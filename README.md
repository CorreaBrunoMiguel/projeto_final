# Manutenção Preditiva Industrial

Projeto acadêmico de análise de dados e classificação de falhas mecânicas, desenvolvido para a atividade **Desenvolvimento de IA para Análise Preditiva [T3]**, do SENAI.

A proposta é usar medidas de sensores e informações do equipamento para comparar dois classificadores: **K-Nearest Neighbors (KNN)** e **Árvore de Decisão**. A variável alvo é `falha_maquina`, em que **0 indica funcionamento normal** e **1 indica falha**.

## Dados e organização

A base fornecida na atividade contém 10.000 registros, dos quais 339 representam falhas (3,39%). As informações usadas na modelagem incluem temperaturas do ar e do processo, velocidade de rotação, torque, desgaste da ferramenta e tipo do equipamento (L, M ou H).

Os identificadores e as colunas que descrevem motivos de falhas foram excluídos dos preditores. O arquivo original é mantido sem alterações.

| Arquivo | Conteúdo |
| --- | --- |
| [notebooks/manutencao_preditiva.ipynb](notebooks/manutencao_preditiva.ipynb) | Análise, preparação dos dados, treinamento e avaliação |
| [data/manutencao_preditiva.csv](data/manutencao_preditiva.csv) | Base original fornecida na atividade |
| [requirements.txt](requirements.txt) | Bibliotecas e versões do ambiente utilizado |
| [docs/enunciado-projeto.md](docs/enunciado-projeto.md) | Requisitos e critérios de avaliação |
| [docs/referencias/anotacoes-engenharia.docx](docs/referencias/anotacoes-engenharia.docx) | Descrição das variáveis e orientações de uso |

## Etapas da análise

O notebook está organizado em sete fases:

1. **Análise exploratória:** dimensões, tipos de dados, estatísticas descritivas, distribuição do torque, proporção de falhas e correlações.
2. **Limpeza e tratamento:** verificação de duplicados, análise de valores extremos e imputação de valores ausentes. As médias e a mediana utilizadas são calculadas somente no treino e aplicadas também ao teste.
3. **Engenharia de atributos:** criação da potência mecânica em watts, a partir do torque e da velocidade de rotação: `potencia = torque × rpm × (2π / 60)`.
4. **Divisão e balanceamento:** separação estratificada em 80% para treino e 20% para teste, codificação do tipo em variáveis binárias e subamostragem apenas no treino. O treino reamostrado fica com 1.355 registros, sendo 20% de falhas.
5. **Escalonamento:** aplicação do `StandardScaler` às variáveis contínuas do KNN, ajustado no treino reamostrado. A árvore utiliza os atributos sem escalonamento.
6. **Ajuste de hiperparâmetros:** comparação de K = 3, 5 e 7 no KNN e de profundidades 3, 5 e sem limite na árvore, com acurácias de treino e teste.
7. **Avaliação final:** comparação dos modelos selecionados, matrizes de confusão, precisão e recall da classe de falha.

As decisões e a interpretação dos resultados estão explicadas junto às células do notebook. O desenvolvimento foi organizado em branches por etapa, com integração em `develop` por pull requests e entrega final em `main`.

## Resultados

O conjunto de teste contém 2.000 registros, incluindo 68 falhas, e mantém sua composição original.

| Modelo | Configuração | Acurácia no teste | Precisão da falha | Recall da falha |
| --- | --- | --- | --- | --- |
| KNN | K = 7 | 95,10% | 38,28% | 72,06% |
| Árvore de decisão | `max_depth = 3` | 96,40% | 47,37% | 52,94% |

Pelo critério de acurácia exigido na atividade, a escolha final é a árvore com profundidade 3. Ela teve menos alertas falsos (40, contra 79 do KNN), mas detectou menos falhas: 36 das 68, enquanto o KNN detectou 49.

Como a classe normal é predominante, prever sempre funcionamento normal daria 96,60% de acurácia no teste, sem detectar nenhuma falha. Por isso, a comparação também considera as métricas da classe de interesse.

## Tecnologias

Python, JupyterLab, pandas, NumPy, Matplotlib, Seaborn, scikit-learn e imbalanced-learn. O Jinja2 é usado na apresentação das tabelas com `pandas.Styler`.

O ambiente utilizado tem **Python 3.13.14**. As versões das bibliotecas estão em `requirements.txt`.

## Como executar

As instruções abaixo são para Linux, com Git e Python 3.13 instalados. Confira a versão de Python antes de criar o ambiente.

```bash
git clone https://github.com/CorreaBrunoMiguel/projeto_final.git
cd projeto_final

python --version
python -m venv .venv
source .venv/bin/activate

python -m pip install -r requirements.txt
python -m ipykernel install --user --name projeto_final --display-name "Python (projeto_final)"
jupyter lab
```

No JupyterLab, abra `notebooks/manutencao_preditiva.ipynb`, selecione o kernel **Python (projeto_final)**, reinicie o kernel e execute todas as células na ordem.

O notebook lê a base por um caminho relativo à pasta `notebooks`. Mantenha a organização das pastas ao executar o projeto.

## Limitações e possíveis melhorias

Os resultados vêm de uma única divisão dos dados. A exploração da base completa e o uso do teste para escolher hiperparâmetros limitam a independência da avaliação. A escolha acadêmica do modelo também não demonstra que ele esteja pronto para uso industrial.

Para continuar o estudo, seria possível:

- Separar uma etapa de validação para selecionar hiperparâmetros e reservar o teste para a avaliação final.
- Comparar outras estratégias de reamostragem e medir o efeito da potência no desempenho.
- Avaliar os custos de falhas não detectadas e alertas falsos para orientar a escolha do modelo.

## Autor

[Bruno Miguel Corrêa](https://github.com/CorreaBrunoMiguel)
