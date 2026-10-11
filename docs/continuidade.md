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

**Etapa:** preparação concluída para iniciar P01; backlog criado, sem implementação do notebook iniciada.

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

**Próxima ação:** iniciar [P01 — Preparar a estrutura do notebook principal](https://github.com/CorreaBrunoMiguel/projeto_final/issues/7), criando a branch feat/p01-notebook-base a partir de origin/develop atualizada. Nenhuma implementação do notebook foi feita por Orion.

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

Atualizar o estado ao encerrar uma demanda. Acrescentar ao registro somente decisões ou intervenções que mudem a construção. Em um novo Work, ler este documento, o enunciado e a issue ativa, conferir o estado remoto e retomar a próxima ação.
