# Continuidade do projeto

Registro administrativo mantido por Orion para orientar Bruno e permitir retomadas entre Works. A referência dos requisitos é o [enunciado original](enunciado-projeto.md). Este registro documenta acordos e estado; as análises e justificativas técnicas da solução pertencem ao notebook de Bruno.

## Referências e prazo

- Repositório: https://github.com/CorreaBrunoMiguel/projeto_final
- Quadro: https://github.com/users/CorreaBrunoMiguel/projects/4
- Dados originais: `data/manutencao_preditiva.csv`.
- Anotações da engenharia: `docs/referencias/anotacoes-engenharia.docx`.
- Prazo vigente informado por Bruno: **13/10/2026**, terça-feira. Horário limite ainda não informado.
- A data de 20/07/2026 do enunciado refere-se à primeira turma, conforme esclarecimento de Bruno. Preservar o documento original.
- Reinício do projeto a partir do zero neste repositório. Não importar como concluídas as tarefas do projeto anterior.

## Escopo da entrega

Construir um único notebook Python que apresente as sete fases técnicas do enunciado: EDA; limpeza e tratamento; feature engineering; divisão e balanceamento; escalonamento; ajuste de parâmetros e análise de overfitting; avaliação final.

Entregar também README com problema, técnicas e execução, dependências com versões em `requirements.txt`, dados acessíveis por caminhos relativos e histórico Git organizado. O vídeo exigido pelo enunciado será produzido por Bruno em uma frente separada; sua preparação não faz parte deste trabalho.

A seção 5.1 menciona seis fases, mas a seção 4 e a rubrica enumeram sete. Organizar a solução pelas sete fases explicitamente exigidas. Melhorias podem aperfeiçoar organização, apresentação e rigor, sem substituir requisitos obrigatórios nem ampliar excessivamente o escopo.

O notebook deve ser conciso, legível e fácil de conferir pelo professor. Apresentar resultados relevantes e explicar observações, escolhas e conclusões. A orientação na conversa pode ser mais detalhada do que a documentação final.

## Responsabilidades e interação

**Bruno:** escreve e executa o código, investiga erros, interpreta resultados, fundamenta escolhas e executa os comandos locais de Git. Também configura o Projects pela interface quando orientado.

**Orion:** estrutura e mantém issues, orienta branches e commits, revisa entregáveis e coordena a integração via pull requests. Esclarece conceitos, questiona propostas e indica lacunas técnicas. Mantém este registro administrativo.

- Avançar por etapas, com uma orientação operacional coerente por resposta e espaço para dúvidas.
- Uma issue pode orientar várias células relacionadas do notebook. Não criar uma issue por célula.
- Cada demanda informa objetivo, requisito atendido, sequência de construção, entregável e critérios de conclusão.
- Bruno implementa seguindo os cards; conclusões e decisões dependentes dos dados são formuladas durante a execução.
- Trabalhar em duas passagens dentro de cada PXX: primeiro concluir o código e as inspeções satisfatoriamente; depois organizar as células Markdown nos pontos úteis à leitura. Explicações podem abranger várias células relacionadas.
- Bruno relatou inclinação a incluir textos nos prints. Orion orienta a organização conforme a função: prints curtos para resultados e verificações, tabelas para resumos estruturados e Markdown para interpretações e justificativas. A escolha deve priorizar clareza, sem proibir prints úteis.
- Na P10, reservar o PR de entrega final para uma revisão aprofundada fase a fase, com melhorias pontuais de organização, apresentação e coerência técnica. Essa revisão foi proposta por Bruno em 12/10 e será feita antes da integração final em main, mantendo o escopo e a autoria da implementação.
- As observações de Bruno são checkpoints de entendimento e matéria-prima para a narrativa. Sugestões complementares são discutidas e encaminhadas ao card apropriado, sem abrir automaticamente novas demandas.
- A revisão incide sobre os entregáveis; não há provas, notas ou avaliações de aprendizagem por Orion.
- Quando uma resposta indicar falta de compreensão relevante, esclarecer o ponto antes de avançar.
- Evitar transcrever toda a conversa ou registrar tentativas sem utilidade para a continuidade.

## Uso de IA e autoria

O enunciado restringe o uso de IA a consulta teórica, esclarecimento conceitual e exemplos genéricos de sintaxe, proibindo delegar funções ou blocos do projeto.

A orientação deve preservar a implementação de Bruno: conceitos, perguntas, dicas e exemplos genéricos, sem escrever funções ou blocos prontos para compor a solução.

Bruno solicitou apoio na organização de textos a partir de suas próprias observações e respostas. O alcance permitido da revisão editorial não foi confirmado pelo professor; não tratar a geração de células Markdown finais como explicitamente autorizada pelo enunciado. Registrar interpretações e justificativas efetivamente formuladas por Bruno, sem inventar decisões, resultados ou participação.

Este documento e as issues são registros administrativos preparados com IA. Não atribuir sua redação integral a Bruno.

## Fluxo de trabalho

- Criar branches de tarefas a partir de `develop` atualizada.
- Fazer commits pequenos, com mensagens diretas.
- Usar GitHub como canal principal de revisão: Bruno executa do início ao fim em kernel limpo, salva as saídas e envia commit/push na branch da tarefa; informa o hash e o status. Orion revisa esse commit antes do merge. O envio não encerra o card; anexos no chat são alternativa pontual.
- Integrar alterações revisadas por PR em `develop`.
- Preservar as branches após o merge, conforme o enunciado.
- Integrar o projeto final em `main` quando a entrega estiver revisada.
- O enunciado exige repositório público na entrega. A visibilidade observada em 11/10 é privada; sua alteração ainda não foi executada nesta preparação.
- Após a submissão, respeitar a restrição do enunciado sobre alterações até o recebimento da nota.

| Status do quadro | Uso |
| --- | --- |
| A fazer | Demanda planejada, não iniciada. |
| Em andamento | Bruno está construindo o entregável. |
| Em revisão | Entregável enviado para conferência. |
| Concluído | Revisão encerrada e alterações integradas em develop. |

Manter uma demanda de implementação em andamento por vez. Orion gerencia as issues pela conexão GitHub disponível; essa conexão não expõe administração de Projects. A configuração do quadro e mudanças manuais de status são executadas por Bruno conforme orientação.

Bruno confirmou a configuração de entrada automática de issues abertas do repositório, com filtro `is:issue is:open`, e das quatro opções de Status, com A fazer como padrão. Bruno confirmou que a issue P00 apareceu automaticamente na coluna A fazer do Projects #4; a entrada automática e o status inicial foram observados por ele.

## Estado atual

**Etapa:** P06 concluída, revisada no commit `ae17ebc8356c3e5724ea7b14233267551d4e20fe` e integrada em `develop` pelo [PR #25](https://github.com/CorreaBrunoMiguel/projeto_final/pull/25), merge `1f13a8e9037593d82a9329b5bc6dea65fc1d49c9`. A branch `feat/p06-balanceamento-escalonamento` foi preservada. Próxima demanda: P07 (#13); a criação da branch local ainda será confirmada por Bruno. O status visual do Projects é atualizado por Bruno.

**Ambiente informado pelo terminal de Bruno:**

| Item | Valor |
| --- | --- |
| Sistema | Linux local |
| Ambiente Conda ativo | SC_TECH |
| Python | 3.13.14 |
| Interpretador | /home/bruno/anaconda3/envs/SC_TECH/bin/python |
| JupyterLab | 4.6.2 |
| Repositório local | /home/bruno/Desktop/senai/projeto_final |

Os caminhos absolutos acima identificam o ambiente administrativo; não devem ser usados na leitura de dados do notebook. O kernelspec sc_tech foi conferido por Bruno: nome de exibição **Python SC_TECH**, com argv apontando para o interpretador do ambiente acima. As importações de NumPy, pandas, Matplotlib, Seaborn, scikit-learn e imbalanced-learn passaram. Versões informadas: NumPy 2.5.1; pandas 3.0.5; Matplotlib 3.11.1; Seaborn 0.13.2; scikit-learn 1.9.0; imbalanced-learn 0.14.2; ipykernel 7.3.0. A execução do notebook no kernel será conferida durante a construção.

**Concluído:** enunciado preservado; repositório clonado por Bruno; CSV e anotações enviados no commit `3293f00778755a9e0cacf13682aa938f0e6959d2` e integrados em develop pelo PR #3; integridade dos dois arquivos conferida por hashes Git; quadro criado e configurações informadas por Bruno.

**Última demanda administrativa:** [P00 — Registrar acordos e continuidade](https://github.com/CorreaBrunoMiguel/projeto_final/issues/4), concluída com documento integrado e entrada automática confirmada por Bruno.

**Último entregável revisado:** [P06 — Preparar representações, balancear o treino e escalonar o KNN](https://github.com/CorreaBrunoMiguel/projeto_final/issues/12), commit `ae17ebc8356c3e5724ea7b14233267551d4e20fe`, obtido diretamente da branch remota após Bruno informar o status sincronizado. O notebook tem 48 células, com 24 células de código preenchidas e saídas de execução 1–24 sem erros. Orion reproduziu as 24 células com o CSV cujo hash Git corresponde ao repositório, em Python 3.12.14, pandas 2.2.3, scikit-learn 1.8.0 e imbalanced-learn 0.14.2, ambiente distinto do SC_TECH. Foram conferidos os registros sorteados, proporção, contagens, preservação de X/y e do teste, índices, nomes e ordem das colunas, finitude, dummies válidas e inalteradas, dados da árvore sem escala e ajuste/transformação corretos do scaler.

**Achados e decisões da P06:** `tipo` recebeu três dummies L/M/H, com categorias fixadas por `CategoricalDtype`. Bruno discutiu a perda de informação no under sampling e a interpolação inválida de categorias no SMOTE padrão. Após questionar a obrigatoriedade, escolheu redução parcial: `RandomUnderSampler(sampling_strategy=0.25, random_state=1986, replacement=False)`, somente no treino. A razão 1:4 produz 1.084 registros normais e 271 falhas (20% do treino), total 1.355; o teste conserva 1.932 normais e 68 falhas, total 2.000. A escolha cumpre a reamostragem exigida sem presumir proporção ótima ou ganho de desempenho. `X_train_knn` e `X_test_knn` são cópias com StandardScaler nas seis contínuas; ajuste somente no treino reamostrado e transformação do teste com os mesmos parâmetros. As dummies ficam em 0/1. A árvore usa `X_train_resampled` e `X_test`, sem escala; ambos os modelos usarão `y_train_resampled` e `y_test`. As médias padronizadas são próximas de zero e os desvios populacionais próximos de um. O arredondamento e a remoção do sinal de zero negativo ocorrem somente na tabela de apresentação. Bruno implementou o código; Orion organizou os três textos das Fases 4 e 5.

**Achados e decisões da P05:** Bruno adotou potência mecânica de rotação, calculada como torque × rpm × (2π/60), em watts. A transformação determinística foi aplicada igualmente a treino e teste já imputados. A feature explicita uma interação multiplicativa com significado físico, sem acrescentar uma medição independente nem garantir melhoria preditiva. Não há NaN ou infinitos; os intervalos são 1.148,44–10.469,92 W no treino e 2.649,96–10.233,15 W no teste. Os imports de NumPy e pi estão na célula inicial. Orion organizou a narrativa; Bruno implementou o código. Nenhuma feature histórica proibida foi usada.

**Achados e decisões da P04:** não há duplicados; foram preservados os extremos de torque e rotação sem alegar causalidade ou erro de medição. As médias/medianas por tipo foram próximas diante da dispersão; foi adotada imputação global por coluna. Temperaturas e torque recebem médias do treino; rotação recebe mediana do treino. Os mesmos quatro valores são aplicados ao teste. A divisão foi antecipada na Fase 2 para evitar vazamento e será reutilizada na Fase 4. A inspeção complementar de falhas por presença de ausências não foi implementada e não é requisito obrigatório. A tabela por tipo e uma repetição no texto do histograma permaneceram no commit; seu corte pode ser considerado em P10. Os textos foram organizados por Orion a partir das decisões discutidas com Bruno, que implementou o código.

**Achados e decisões da P03:** foram implementados histograma geral do torque sem hue, contagem de `falha_maquina` com rótulos Sem falha/Com falha e percentuais sobre as barras, e heatmap de Pearson com as cinco medidas contínuas e o alvo. O torque observado tem média 39,97 N·m, mediana 40,10 N·m e desvio padrão próximo de 10 N·m, com distribuição unimodal aproximadamente simétrica. A classe de falha representa 3,39% da base; a acurácia de 96,61% do preditor constante de classe normal é apenas uma referência no conjunto completo. As temperaturas têm correlação próxima de 0,88; rotação e torque, −0,88; torque e alvo, 0,19. Correlação fraca não fundamenta exclusão automática nem mede importância preditiva. A média foi discutida como candidata à imputação, condicionada à investigação de extremos e diferenças por tipo. As contagens exatas do alvo permanecem na tabela, e o gráfico usa somente percentuais nas anotações. Foi removida a repetição do texto sobre o alvo e explicitada a relação entre os 14 campos do CSV e as 13 colunas mais o índice `udi`.

**Representação e achados da P02:** o CSV original tem 10.000 registros e 14 campos. Bruno passou a usar `udi` como índice na leitura; `df` tem 13 colunas de dados, mais o índice. `df_origin` guarda a leitura e `df` é a cópia de trabalho. As ausências das duas temperaturas, rotação e torque coincidem em 500 linhas (5%); as quatro medidas estão presentes nas outras 9.500 linhas. O alvo está completo: 9.661 registros normais e 339 falhas (3,39%). Tipos L/M/H: 6.000/2.997/1.003 registros e 235/83/21 falhas. Os textos documentam identificadores, medidas, categoria, alvo e proibição de usar os cinco indicadores históricos como preditores ou em atributos derivados.

**Próxima ação:** Bruno atualiza as referências remotas, cria `feat/p07-knn` a partir de `origin/develop` e confirma o status. Retomar [P07 — Treinar as configurações do KNN e registrar acurácias](https://github.com/CorreaBrunoMiguel/projeto_final/issues/13), na Fase 6: escolher pelo menos três valores ímpares de K, treinar com `X_train_knn`/`y_train_resampled`, medir treino e teste e guardar modelos/resultados. Tornar explícita a convenção da acurácia de treino. A composição de classes difere entre treino reamostrado (20% de falhas) e teste (3,4%); diferenças de acurácia não isolam, sozinhas, sobreajuste. Se o teste orientar a escolha de K, registrar a limitação prevista no card, sem chamá-lo de validação independente. Avançar por partes e preservar a autoria de Bruno.

## Plano de execução

As demandas são sequenciais; os cards contêm o roteiro completo e a conversa avança por partes. Manter somente uma demanda de implementação em andamento. A divisão foi preparada a partir do enunciado, das anotações da engenharia e do cabeçalho do CSV; a análise estatística será feita por Bruno.

| Demanda | Issue | Branch |
| --- | --- | --- |
| P01 — Preparar a estrutura do notebook principal | [#7](https://github.com/CorreaBrunoMiguel/projeto_final/issues/7) | `feat/p01-notebook-base` |
| P02 — Inspecionar os dados e documentar o papel das colunas | [#8](https://github.com/CorreaBrunoMiguel/projeto_final/issues/8) | `feat/p02-inspecao-dados` |
| P03 — Construir os três gráficos de EDA e interpretar os resultados | [#9](https://github.com/CorreaBrunoMiguel/projeto_final/issues/9) | `feat/p03-eda-graficos` |
| P04 — Tratar duplicados, diagnosticar outliers e imputar sem vazamento | [#10](https://github.com/CorreaBrunoMiguel/projeto_final/issues/10) | `feat/p04-tratamento-dados` |
| P05 — Criar e validar uma variável numérica derivada | [#11](https://github.com/CorreaBrunoMiguel/projeto_final/issues/11) | `feat/p05-feature-engineering` |
| P06 — Preparar representações, balancear o treino e escalonar o KNN | [#12](https://github.com/CorreaBrunoMiguel/projeto_final/issues/12) | `feat/p06-balanceamento-escalonamento` |
| P07 — Treinar as configurações do KNN e registrar acurácias | [#13](https://github.com/CorreaBrunoMiguel/projeto_final/issues/13) | `feat/p07-knn` |
| P08 — Treinar as configurações da árvore e comparar generalização | [#14](https://github.com/CorreaBrunoMiguel/projeto_final/issues/14) | `feat/p08-arvore-decisao` |
| P09 — Comparar os melhores modelos e formular o veredito | [#15](https://github.com/CorreaBrunoMiguel/projeto_final/issues/15) | `feat/p09-avaliacao-final` |
| P10 — Revisar reprodutibilidade, README e entrega em main | [#16](https://github.com/CorreaBrunoMiguel/projeto_final/issues/16) | `docs/p10-entrega-final` |

P04 antecipa a divisão antes de aprender as estatísticas de imputação; a Fase 4 documenta a mesma divisão. Essa adequação evita vazamento e preserva as sete fases editoriais. P07–P09 exigem explicitar a limitação se o teste também for utilizado na seleção, conforme a comparação solicitada pelo enunciado.

Referências técnicas: [scikit-learn — práticas e vazamento](https://scikit-learn.org/1.9/common_pitfalls.html) e [imbalanced-learn — reamostragem e vazamento](https://imbalanced-learn.org/stable/common_pitfalls.html).

## Registro breve de decisões

| Data | Interação e decisão |
| --- | --- |
| 11/10/2026 | Bruno decidiu reiniciar no repositório projeto_final, com autoria do código e decisões técnicas próprias, orientação por cards e revisão de entregáveis. |
| 11/10/2026 | Bruno delimitou uma apresentação concisa para o professor e retirou o vídeo do escopo desta frente; esclareceu o prazo vigente de 13/10. |
| 11/10/2026 | Bruno clonou o repositório, organizou os arquivos conforme orientação e enviou o commit 3293f00. Orion conferiu os arquivos contra os anexos e integrou o PR #3. |
| 11/10/2026 | Bruno criou o Projects #4, configurou as quatro colunas e confirmou que P00 apareceu automaticamente em A fazer. |
| 11/10/2026 | Bruno conferiu o kernelspec Python SC_TECH e executou as importações sem erros. Orion leu as fontes e estruturou P01–P10, sem implementar o notebook. |
| 11/10/2026 | A pedido de Bruno, Orion redigiu a apresentação, a introdução, as fontes e os cabeçalhos de P01. Bruno adotou a estrutura, montou e salvou o notebook no JupyterLab e enviou o commit 2a43f89. Orion orientou o .gitignore e conferiu a estrutura. O critério de redação própria da introdução foi ajustado para refletir essa assistência; nenhuma análise, conclusão ou célula de código foi produzida nesta etapa. |
| 11/10/2026 | Bruno escreveu as inspeções de P02, propôs manter uma cópia de trabalho e confirmou pela contagem por linha que as ausências coincidem. Construiu os resumos global e por tipo, incluindo taxas de falha, e identificou o desbalanceamento do alvo. Orion forneceu orientação conceitual e organizou os textos a partir desses checkpoints e das fontes; Bruno inseriu os textos e enviou o commit 5d12c30, usando udi como índice. |
| 11/10/2026 | Bruno definiu a narrativa após a conclusão do código de cada PXX e escolheu GitHub como canal principal de revisão. Sugeriu comparar falhas nos registros com ausências; Orion encaminhou e registrou esse diagnóstico complementar no card P04 (#10). Comparar a base antes/depois do tratamento permanece uma sugestão a discutir em P04, não uma nova demanda obrigatória. |
| 11/10/2026 | Bruno implementou os três gráficos de P03, discutiu a leitura global e por tipo/falha, a limitação da acurácia no desbalanceamento e a limitação de Pearson. Orion organizou as células textuais a partir desses checkpoints, revisou e reproduziu o código. Bruno aplicou os ajustes editoriais e enviou 84e9db4. Orion corrigiu o destino do PR #20 de main para develop, conferiu que restou apenas o notebook no diff, integrou a P03 preservando a branch e encerrou a issue #9. |
| 12/10/2026 | Bruno iniciou P04, manteve udi como índice identificador original e apresentou os diagnósticos iniciais de duplicações e ausentes. Relatou preferência por prints e solicitou orientação de organização; combinou revisão aprofundada fase a fase com melhorias pontuais no PR final. Orion registrou essa revisão na P10, mantendo o foco atual em P04 e o fluxo de código primeiro, narrativa depois. |
| 12/10/2026 | Bruno implementou a P04, escolheu médias para as temperaturas e o torque e mediana para rotação, discutiu e preservou os extremos e inseriu a narrativa organizada por Orion. Enviou 3d637fb e confirmou execução em kernel limpo sem erros. Orion revisou e reproduziu as 17 células, integrou o PR #21 em develop preservando a branch e encerrou a issue #10. Próxima etapa: P05. |
| 12/10/2026 | Bruno implementou e validou a potência mecânica de rotação na P05, com conversão rpm para rad/s. Após revisão de ec4e8e6, atualizou as saídas no commit 25f65ba. Orion reproduziu as 19 células, conferiu a transformação e a preservação dos dados, integrou o PR #23 em develop preservando a branch e encerrou a issue #11. Próxima etapa: P06. |
| 12/10/2026 | Bruno escolheu três dummies para tipo e discutiu as limitações de SMOTE e under sampling. Questionou a necessidade de reamostragem; após conferir a exigência do enunciado e a possibilidade de redução parcial, adotou Random Under Sampling com razão falhas/normais 0,25. |
| 13/10/2026 | Bruno concluiu o StandardScaler nas contínuas do KNN, inseriu os textos das Fases 4 e 5 e enviou a P06 na branch sincronizada. Orion obteve ae17ebc pelo remoto, reproduziu as 24 células, integrou o PR #25 em develop preservando a branch e encerrou a issue #12. Próxima etapa: P07. |

Atualizar o estado ao encerrar uma demanda. Acrescentar ao registro somente decisões ou intervenções que mudem a construção. Em um novo Work, ler este documento, o enunciado e a issue ativa, conferir o estado remoto e retomar a próxima ação.
