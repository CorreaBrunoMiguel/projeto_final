# P10 — Roteiro de revisão técnica, narrativa e entrega

**Projeto:** Manutenção Preditiva Industrial — SENAI T3  
**Autor da implementação:** Bruno Miguel Corrêa  
**Responsável pelo roteiro e orientação:** Orion, com assistência de IA  
**Preparado em:** 13/10/2026  
**Situação:** R00 concluída para o anexo de 13/10/2026; R01–R16 pendentes.

## 1. Objetivo e limites

Revisar o notebook completo como uma exposição técnica concisa: o leitor deve localizar o problema, entender cada escolha, conferir sua implementação e relacionar os resultados ao veredito. O público é um avaliador com conhecimentos de Python, estatística e classificação supervisionada.

Este documento organiza trabalho futuro. Não altera o notebook, não valida a versão local ainda não publicada e não autoriza iniciar todas as etapas de uma vez.

Manter as escolhas já aceitas: imputação global por média/mediana; split estratificado 80/20; potência mecânica; três dummies de tipo; RandomUnderSampler com razão 0,25; StandardScaler nas contínuas do KNN; K = 3, 5, 7; árvores com profundidades 3, 5 e None. Uma alteração metodológica só será proposta se uma verificação demonstrar erro ou incompatibilidade material. Não buscar novas configurações para melhorar resultados no teste já consultado.

Matriz de confusão, precisão e recall são complementos aprovados. Não acrescentar automaticamente F1, ROC, PR-AUC, novos modelos, validação cruzada, novos atributos ou novos experimentos. Melhorias metodológicas não implementadas podem aparecer como limitações ou trabalho futuro.

Bruno implementa e executa o código. Orion orienta e revisa por partes e auxilia a organização textual a partir de decisões realmente discutidas. O enunciado, seção 8, restringe IA a consulta teórica, esclarecimentos e exemplos genéricos: este roteiro não contém blocos prontos de implementação. Não atribuir a Bruno a redação integral preparada por IA nem supor que o professor autorizou toda forma de revisão editorial.

## 2. Fontes e estado de referência

### Fontes de autoridade

| Fonte | Papel na revisão |
| --- | --- |
| [Enunciado preservado](https://github.com/CorreaBrunoMiguel/projeto_final/blob/f0c2b9051f6687a8d41a7a75cc1822b7ae3e4db5/docs/enunciado-projeto.md) | Requisitos, rubrica, formato, Git e entrega. |
| [Anotações da engenharia](https://github.com/CorreaBrunoMiguel/projeto_final/blob/f0c2b9051f6687a8d41a7a75cc1822b7ae3e4db5/docs/referencias/anotacoes-engenharia.docx) | Significado das colunas, unidades e exclusão dos cinco motivos históricos de falha. |
| [Notebook remoto de referência](https://github.com/CorreaBrunoMiguel/projeto_final/blob/f0c2b9051f6687a8d41a7a75cc1822b7ae3e4db5/notebooks/manutencao_preditiva.ipynb) | Implementação e saídas da P09: 58 células, sendo 30 de código. |
| Notebook local de Bruno na branch docs/p10-entrega-final | Versão de trabalho a ser obtida na R00; prevalece para revisar as alterações da P10. |
| [Issue P10](https://github.com/CorreaBrunoMiguel/projeto_final/issues/16) | Acordos de interação e acompanhamento; não substitui requisitos nem evidência executada. |
| Documentação oficial das bibliotecas, seção 9 deste roteiro | Verificação de comportamento das APIs e limites metodológicos. |

A leitura preparatória cobriu todas as células da versão remota, o enunciado, a continuidade e as anotações da engenharia disponíveis. A preparação não reproduziu novamente o notebook nem inspecionou visualmente todos os seus gráficos. Essas verificações pertencem às etapas abaixo.

Na conversa, Bruno apresentou as matrizes de confusão, precisão, recall e a tabela consolidada. O novo veredito foi proposto, mas sua inclusão não foi confirmada. Essas alterações ainda não estão na versão remota acima. Conferir o arquivo local antes de editar: não repetir automaticamente instruções já aplicadas.

### Tratamento de divergências do enunciado

- Preservar as sete fases da seção 4 e da rubrica. A menção a seis fases na seção 5.1 é uma inconsistência editorial.
- Manter a divisão antes de calcular a imputação, embora os títulos acadêmicos apareçam em outra ordem. Explicar a antecipação e reutilizar o mesmo split na Fase 4.
- A rubrica pede indicar o modelo com maior acurácia. Preservar essa resposta e separar a recomendação acadêmica da adoção industrial.
- Substituir promessas de “estabilidade garantida” por descrição do melhor desempenho observado. Uma única divisão e a consulta ao teste não demonstram estabilidade.
- O prazo original de 20/07/2026 pertence à primeira turma, segundo o registro de continuidade. O prazo informado para esta entrega é 13/10/2026; o horário vigente continua sem confirmação. Não reescrever a fonte original nem deduzir esse horário.
- O critério do README remete a um item 4.3 inexistente; usar os tópicos efetivos da seção 5.2.

Classificar cada ponto como **obrigatório**, **adaptação tecnicamente justificada**, **complemento aprovado** ou **melhoria opcional**. Não transformar exemplos do enunciado em exigências inexistentes.

## 3. Padrão de revisão e narrativa

Cada unidade de análise seguirá, quando pertinente:

1. **Pergunta ou finalidade:** por que esta etapa existe.
2. **Decisão:** o que foi escolhido e com qual fundamento.
3. **Implementação:** célula Python responsável.
4. **Evidência:** saída, tabela, figura ou verificação suficiente.
5. **Interpretação e limite:** o que a evidência permite concluir.
6. **Transição:** relação com a próxima transformação, se necessária.

Não criar seis subtítulos em cada célula. Esse é um critério de conteúdo, não um molde repetitivo. Preferir uma explicação curta antes da operação e uma interpretação curta depois de sua evidência.

### Regras editoriais

- Descrever o trabalho executado, sem promessas futuras já ultrapassadas.
- Usar linguagem técnica direta, sem transformar o notebook em tutorial de sintaxe.
- Explicar escolhas; evitar narrar linha a linha o código.
- Agrupar células curtas que respondem à mesma pergunta; separar operações com finalidades diferentes.
- Prints curtos para verificações; tabelas para comparações; Markdown para interpretação.
- Manter precisão numérica nos objetos e arredondar somente na apresentação.
- Padronizar “normal”, “falha”, “treino reamostrado”, “teste preservado”, unidades e nomes.
- Não repetir a mesma ressalva em cada subseção: registrar o método de avaliação em um ponto visível e retomá-lo no veredito.
- Não alegar causalidade, ganho preditivo, ausência de vazamento em todo o experimento ou prontidão industrial sem evidência.
- A base permite classificar o estado indicado pelo alvo. Não afirmar previsão antecipada com horizonte temporal, acompanhamento de máquinas ou validação industrial sem dados que sustentem isso.
- Manter poucas verificações úteis; evitar arquitetura, funções auxiliares ou suítes de testes que apenas repitam o código.

### Forma de interação em cada etapa

Orion apresenta o diagnóstico do recorte, identifica a célula pelo título/conteúdo e indica uma primeira alteração coerente. Bruno aplica, executa e devolve a evidência. Orion confere e só então avança dentro da etapa ou encerra o recorte. Uma etapa pode ocupar várias respostas.

Registrar para cada mudança: localização, problema, ação — manter, reescrever, mover, juntar, excluir ou acrescentar —, motivo e evidência de aceite. O registro é administrativo e não será copiado para a entrega.

Os prompts abaixo iniciam recortes; não obrigam a executar todo o recorte em uma única resposta. Toda retomada herda os limites deste roteiro.

## 4. Matriz de cobertura

| Exigência ou complemento | Evidência de aceite | Etapas |
| --- | --- | --- |
| Problema, alvo, fontes e papel das colunas | Introdução curta; alvo 0/1; unidades; restrições localizáveis | R01–R02 |
| Dimensões, dtypes e describe | Saídas visíveis; 14 campos originais versus 13 colunas com udi no índice | R02 |
| Três gráficos e interpretação | Histograma, barras do alvo e Pearson legíveis, com leitura analítica | R03 |
| Duplicidades, ausências e boxplots | Operação de deduplicação, diagnóstico, imputação justificada e análise de extremos | R04–R05 |
| Novo atributo válido | Fórmula e unidade, nulos tratados antes, transformação igual nos dois conjuntos | R06 |
| X/y, 80/20 e stratify=y | Split único; alinhamento; conjuntos sem índices compartilhados | R05 |
| Reamostragem somente no treino | Classes antes/depois; teste preservado; razão explicada | R07 |
| StandardScaler apenas nas contínuas do KNN | Ajuste no treino, transformação no teste, árvore sem escala | R08 |
| Três K ímpares e três profundidades | Tabelas de acurácia de treino/teste e interpretação de sobreajuste | R09–R10 |
| Acurácia final e modelo indicado | Tabela final e conclusão acadêmica explícita | R11–R12 |
| Matrizes, precisão e recall aprovados | Contagens reconciliadas; classe positiva 1; tabela consolidada | R11 |
| Notebook único e explicativo | Ordem executável; narrativa coerente; saídas salvas | R13–R16 |
| Dependências e caminhos relativos | requirements com versões; execução em ambiente recriado | R14–R16 |
| README | Problema, técnicas, estrutura, execução, resultados, limites e melhorias | R14 |
| Git e limpeza da entrega | PRs, branches preservadas, main com apenas arquivos pertinentes | R15–R16 |
| Repositório público, vídeo e AVA | Verificação explícita das obrigações externas; sem conclusão presumida | R16 |

Vídeo e submissão são uma frente de Bruno. O roteiro verifica sua situação ao encerrar, sem produzir o vídeo ou tratar sua existência como confirmada.

## 5. Sequência de etapas e prompts

As posições citadas são da versão remota de 58 células, contadas a partir de 1. Após inclusões ou movimentos, usar títulos, variáveis e IDs para localizar o recorte. Todas as etapas começam pendentes.

### R00 — Fixar a versão real de trabalho

**Recorte:** notebook local completo, status e diff da branch docs/p10-entrega-final.

**Revisão:** obter o notebook atualizado por anexo ou commit de Bruno; comparar com a referência remota; localizar mudanças da introdução, deduplicação, matrizes, métricas, consolidação e veredito. Atualizar o mapa das células antes de recomendar alterações.

**Aceite:** uma versão inequívoca para revisar, com origem identificada; alterações locais preservadas; pendências diferenciadas de mudanças já feitas. Não declarar revisão final com base somente no histórico da conversa.

**Prompt:**

> Inicie apenas a R00 do roteiro P10. Confira a versão atual do meu notebook e suas diferenças em relação à P09. Identifique o que já foi aplicado e o que ainda falta, sem iniciar correções de outra etapa.

### R01 — Abertura, fontes e preparação do ambiente

**Recorte:** células 1–7; Introdução, Fontes do projeto e imports.

**Revisão:** reduzir a abertura a problema, alvo, objetivo e comparação. Conferir o tempo verbal já corrigido localmente. Separar preparação do ambiente da EDA quando isso melhorar a leitura. Incluir os imports efetivamente usados na avaliação ampliada; revisar importações sem uso, separadores decorativos e impressão do caminho pessoal. Conferir leitura relativa e preservação de df_origin.

**Aceite:** leitor sabe o que será avaliado; ambiente e dados são identificáveis; preparação não depende de paths pessoais; nomes e unidades conferem com a engenharia.

**Prompt:**

> Execute a R01: revise a abertura, as fontes e a preparação do ambiente. Mostre o primeiro ajuste necessário e seu motivo, com localização precisa. Preserve meu código e aguarde minha aplicação antes de avançar.

### R02 — Inspeção, contrato de dados e ausências

**Recorte:** células 7–13; papel das colunas, shape, dtypes, describe, padrão de ausências e resumos.

**Revisão:** conferir indexação por udi, unicidade, categorias, alvo e cinco preditoras operacionais. Garantir que indicadores históricos e identificadores não entrem nos modelos ou na potência. Diferenciar descrição numérica de códigos e de medidas. Tornar a saída de ausências por linha autoexplicativa. Avaliar a utilidade da tabela por tipo; manter apenas se apoiar uma decisão ou interpretação, sem corte automático.

**Aceite:** 10.000 registros, 14 campos no CSV e 13 colunas mais índice ficam claros; os 500 registros com quatro ausências simultâneas são rastreáveis; o contrato de entradas está explícito.

**Prompt:**

> Execute apenas a R02. Confira inspeção, contrato das colunas e diagnóstico das ausências. Identifique redundâncias e lacunas de evidência; indique uma primeira correção sem iniciar os gráficos.

### R03 — EDA: pergunta, gráfico e interpretação

**Recorte:** células 14–19; histograma do torque, barras do alvo e heatmap.

**Revisão:** cada gráfico deve responder a uma pergunta e sustentar uma escolha. Conferir títulos, eixos, unidades, denominadores, cores e leitura em tamanho normal. Histograma usa valores observados; correlações ignoram ausências nas observações disponíveis por par, não são calculadas sobre dados já imputados. Distinguir associação linear, causalidade e importância preditiva. Retirar promessas de avaliação de importância que não foram realizadas.

**Aceite:** três gráficos preservados e legíveis; interpretações conferem com saídas; 96,61% refere-se à base completa e não é confundido com o baseline de 96,60% no teste.

**Prompt:**

> Execute a R03, começando pelo histograma. Revise pergunta analítica, figura e interpretação como uma unidade. Depois da minha correção e sua conferência, passe às barras e ao heatmap, sem adicionar novos gráficos automaticamente.

### R04 — Duplicidades, domínios e valores extremos

**Recorte:** células 21–25; diagnóstico de integridade, ausências, categorias e boxplots.

**Revisão:** definir o que é uma duplicata nesta base, lembrando que udi está no índice e duplicated não o considera. Tornar a remoção explícita na cópia df com contagem antes/depois, se ainda não implementada. Diferenciar duplicata de linha incompleta. Conferir domínio das categorias/alvo e preservar os boxplots anteriores à imputação. Justificar retenção de extremos sem chamar todo ponto fora dos bigodes de erro.

**Aceite:** df_origin intacto; zero remoções nesta base; 10.000 linhas preservadas; ausência de duplicatas não substitui a demonstração da operação. Extremos e decisão de mantê-los estão documentados.

**Prompt:**

> Execute a R04. Revise primeiro o significado e o tratamento de duplicidades, preservando df_origin. Oriente minha implementação e verifique a saída; depois revise domínios e boxplots.

### R05 — Split antecipado e imputação

**Recorte:** células 26–31; colunas_preditoras, X/y, train_test_split, estatísticas por tipo e base_imputacao.

**Revisão:** conferir split único com test_size=0.2, stratify=y e semente 1986. Preservar verificações de alinhamento e disjunção, reduzindo prints extensos. Manter uma evidência suficiente para imputação global em vez de por tipo. Conferir média para temperaturas/torque e mediana para rotação, calculadas somente no treino e aplicadas igualmente ao teste. Expor os valores de preenchimento se a escolha ainda estiver sem saída verificável. Reconhecer que a imputação substitui medições e que quatro ausências conjuntas criam uma concentração artificial.

A EDA examinou a base inteira e influenciou decisões. Não confundir proteção dos cálculos de imputação com independência completa do teste em todo o processo.

**Aceite:** 8.000/2.000 registros; alinhamento correto; nenhum índice compartilhado; nenhuma estatística de preenchimento calculada no teste; nenhum nulo nas entradas preparadas. Sem novo sorteio na Fase 4.

**Prompt:**

> Execute a R05 em dois recortes: primeiro seleção de entradas e split; depois imputação e justificativas. Explique a antecipação da divisão e confira de onde vêm as estatísticas. Mantenha a estratégia aceita.

### R06 — Engenharia de atributos

**Recorte:** células 33–35; potencia_mecanica_w, amostra e verificações.

**Revisão:** explicitar P = torque × rpm × 2π/60 e unidade W. Conferir execução após imputação, transformação igual nos dois conjuntos e ausência de históricos proibidos. Enxugar a saída de mínimos/máximos e a precisão excessiva sem alterar dados. Descrever potência como interação derivada, sem ganho preditivo demonstrado ou nova medição independente.

**Aceite:** fórmula coerente, valores finitos e sem nulos; código e amostra concordam; nenhuma avaliação de benefício inventada.

**Prompt:**

> Execute a R06. Revise fórmula, significado físico, código, verificações e narrativa da potência. Preserve o atributo e indique somente ajustes necessários para clareza e correção.

### R07 — Codificação e reamostragem

**Recorte:** células 37–41; CategoricalDtype, get_dummies, RandomUnderSampler e contagens.

**Revisão:** categorias L/M/H fixas e mesmas colunas na mesma ordem em treino/teste. Corrigir o print que fala apenas em “mesmo número” enquanto verifica igualdade das colunas. Confirmar que as três dummies representam categorias sem ordem artificial. Uma categoria desconhecida não pode ser convertida silenciosamente em ausência sem verificação de domínio.

Explicar razão minoritária/majoritária 0,25: uma falha por quatro normais, ou 20% de falhas no treino resultante. Quantificar a redução quando apoiar a justificativa. Não descrever a amostragem como proporcionalmente ótima nem como preservação garantida da diversidade. Conferir alinhamento e teste intacto.

**Aceite:** treino original 7.729 normais/271 falhas; reamostrado 1.084/271; teste 1.932/68. Perda de 6.645 normais, equivalente a 83,06% de todo o treino, identificada como limitação.

**Prompt:**

> Execute a R07, primeiro nas dummies e depois na reamostragem. Confira representação, alinhamento e contagens, e deixe explícito o significado de 0,25 e sua perda de informação, sem substituir o método.

### R08 — Escalonamento e entradas dos dois modelos

**Recorte:** células 43–45; contínuas, cópias KNN, scaler e resumo_knn.

**Revisão:** seis contínuas padronizadas; três dummies intactas; scaler ajustado no treino reamostrado e reutilizado no teste. Árvore recebe a representação sem escala. Justificar o comportamento dos cortes de uma árvore sob padronização, evitando afirmação universal sobre toda transformação ou equivalência numérica perfeita. Conferir que o arredondamento do resumo não modifica os dados usados no fit.

**Aceite:** correspondência de linhas, alvo, colunas e ordem; médias do treino escalonado próximas de zero e desvios populacionais próximos de um; não exigir essas mesmas estatísticas do teste.

**Prompt:**

> Execute a R08. Confira o percurso das duas representações, a origem do ajuste do scaler e as verificações. Revise a justificativa da árvore e preserve a padronização apenas das contínuas do KNN.

### R09 — Experimentos com KNN

**Recorte:** células 47–50; laço, modelos_knn, resultados_knn e interpretação.

**Revisão:** K = 3, 5, 7, votação uniforme e mesmas entradas. Modelos permanecem armazenados; acurácias usam treino reamostrado e teste preservado. Eliminar repetição desnecessária de formatação sem criar abstrações. Identificar que acurácia de treino inclui o próprio registro entre os vizinhos; não a apresentar como validação independente. Conservar o melhor K observado, sem atribuir estabilidade ou sobreajuste comprovado somente à diferença dos scores.

**Aceite:** resultados salvos e código concordam; seleção de K=7 tem critério explícito; diferentes prevalências de classes e consulta ao teste são reconhecidas.

**Prompt:**

> Execute a R09. Revise treinamento, tabela e interpretação do KNN, preservando os três K. Identifique o primeiro ajuste necessário para distinguir desempenho observado, treino e seleção.

### R10 — Árvores e síntese dos hiperparâmetros

**Recorte:** células 51–54; profundidades, modelos_arvore, resultados_arvore e interpretação conjunta.

**Revisão:** profundidades 3/5/None e semente fixa; mesmos registros/atributos da comparação; sem escala. Manter None como parâmetro e “Sem limite” somente no rótulo. Conferir indícios de sobreajuste: aumento do ajuste ao treino com piora do teste relativo à profundidade 3, sem afirmar causalidade demonstrada ou estabilidade futura. Concentrar as ressalvas compartilhadas em uma síntese curta.

O gráfico de acurácia por hiperparâmetro permanece opcional. Só incluir se simplificar a leitura; utilizar tabelas existentes e preservar os números.

**Aceite:** três configurações, scores de treino/teste, melhor profundidade observada e justificativa acadêmica localizáveis; texto não promete mais do que os resultados.

**Prompt:**

> Execute a R10. Revise as árvores e a síntese da Fase 6. Confira None, critérios de seleção e interpretação de sobreajuste; reduza repetições mantendo as ressalvas metodológicas necessárias.

### R11 — Avaliação por classe e tabela final

**Recorte:** Fase 7 inteira até o veredito; inclui células locais ainda não presentes na referência remota.

**Revisão:** sequência preferencial: recuperar modelos; prever uma vez em cada representação; exibir matrizes; calcular métricas; apresentar uma tabela final consolidada. Evitar uma tabela final apenas com acurácia seguida de outra quase igual. A tabela isolada de precisão/recall pode ser absorvida pela consolidada, preservando objetos úteis.

Fixar classes [0,1], linhas reais e colunas previstas. Confirmar que previsões seguem a ordem de y_test; nomes de apresentação não devem determinar silenciosamente identidade de modelos. O map baseado em recortar strings funciona nos nomes apresentados, mas é frágil: avaliar chave explícita ou correspondência documentada e verificar ausência de NaN/duplicidade. Não gerar uma biblioteca de avaliação.

Precisão = TP/(TP+FP); recall = TP/(TP+FN); acurácia = (TN+TP)/total. Positivo é 1; percentuais apenas na exibição. Não inventar precisão para baseline que não emite alertas; ela é indefinida.

**Aceite:** somas das matrizes reconciliam classes e total; scores reconciliam diagonais; métricas conferem com denominadores. Os valores da seção 7 são referências da conversa, não resultados que devem ser forçados pelo código.

**Prompt:**

> Execute a R11 na versão atual. Revise em sequência previsões, matrizes, métricas e consolidação. Confira os cálculos a partir das contagens e elimine duplicação de apresentação, sem mudar os modelos ou acrescentar métricas.

### R12 — Veredito e limites da recomendação

**Recorte:** Markdown final da Fase 7 e eventual síntese inicial.

**Revisão:** indicar árvore de profundidade 3 pelo critério acadêmico de acurácia. Contrapor maior recall do KNN e menor número de alertas falsos da árvore com contagens e denominadores. Mostrar baseline normal com alta acurácia e nenhuma falha detectada. Não declarar os modelos inúteis somente por estarem abaixo do baseline em acurácia, nem prontos para a empresa.

Custos de falso negativo/falso positivo não foram fornecidos; recomendação operacional depende disso. As configurações foram escolhidas com consulta ao teste; a EDA também utilizou a base completa. Precisão e recall adicionais não restauram independência do teste.

**Aceite:** conclusão concisa, alinhada à rubrica e às métricas, sem repetir toda a tabela em prosa. Distinguir seleção acadêmica, resultado observado e decisão industrial. Confirmar se o veredito proposto na conversa foi realmente inserido.

**Prompt:**

> Execute a R12. Confira o veredito atual contra a tabela e as matrizes. Ajude a organizar uma conclusão técnica concisa com seleção acadêmica, troca entre tipos de erro e limites metodológicos, sem inventar custos ou prontidão industrial.

### R13 — Leitura integral e dependências entre células

**Recorte:** notebook completo após R01–R12.

**Revisão:** percorrer a história do início ao fim; títulos, transições, repetições, células vazias, sobras de diagnóstico e nomes sobrescritos. Preservar a distinção de base original, cópia, treino preparado, treino reamostrado e representação KNN. Garantir que a narrativa reflita a sequência real. Verificar se seleções fixas de K/profundidade continuam compatíveis com tabelas; não mascarar divergências.

Conferir metadados de kernel, imports e fontes; mover resultados globais para abertura somente após validados. Não exigir resumo inicial adicional se a conclusão e a introdução já orientarem bem o leitor.

**Aceite:** leitura técnica sem saltos; cada transformação importante tem justificativa; nenhuma variável depende de célula apagada, execução anterior ou objeto criado fora do notebook.

**Prompt:**

> Execute a R13 como revisão integrada, sem reabrir experimentos. Procure rupturas de narrativa, repetições e dependências ocultas; apresente uma correção por vez e confira o efeito sobre o restante.

### R14 — README e ambiente reproduzível

**Recorte:** README, requirements e instrução de execução.

**Revisão:** README com nome/objetivo, problema e alcance, fontes, técnicas usadas, estrutura final prevista, ambiente, instalação, execução, resultados, limitações e melhorias realistas. Evitar transcrição extensa do notebook. Não apresentar pacote de produção, API ou previsão temporal que não existe.

Obter versões do ambiente efetivamente validado, em vez de copiar todo pip freeze/Conda ou inventar versões. Incluir dependências diretas da análise e as necessárias ao fluxo de Jupyter e à apresentação — inclusive suporte a Styler quando necessário. Diferenciar biblioteca padrão de pacotes instaláveis. Documentar Python suportado e kernel selecionado; não depender do nome pessoal SC_TECH.

A leitura atual usa ../data e pressupõe execução a partir de notebooks. Manter instrução explícita e testada; só alterar a estratégia de caminhos se houver benefício concreto.

**Aceite:** terceiro consegue instalar e executar seguindo o README; requisitos correspondem ao ambiente testado; números do README conferem com Fase 7; nenhum caminho pessoal.

**Prompt:**

> Execute a R14. Revise primeiro as dependências reais e o modo de executar; depois organize o README com os tópicos do enunciado e os resultados validados. Oriente minha escrita e não exporte indiscriminadamente meu ambiente.

### R15 — Limpeza obrigatória antes de main

**Recorte:** árvore de arquivos rastreados e não rastreados; referências no notebook/README.

**Revisão:** inventariar e classificar arquivos com os critérios da seção 8. Remover da árvore de entrega continuidade, roteiro e demais registros de interação, além de temporários, ambientes, notebooks alternativos e artefatos de revisão sem função na solução. Adicionar regras específicas de ignore quando pertinentes.

A exclusão local de pastas não rastreadas exige inspeção prévia: anaconda_projects pode conter outros trabalhos. Não apagar cegamente a pasta nem usar uma limpeza ampla do Git. Para pastas rastreadas, remover com diff verificável; para as não rastreadas, ignorar ou remover apenas o conteúdo do projeto confirmado como temporário.

Conferir todos os links antes de remover documentos. Preservar fontes técnicas pertinentes ou substituí-las por referências estáveis; não deixar referências quebradas nem ocultar assistência editorial. Não reescrever histórico, apagar branches ou excluir dados originais.

**Aceite:** inventário final explica o papel de cada arquivo; nenhum registro administrativo na árvore candidata a main; nenhuma dependência ou link removido inadvertidamente. Limpeza ocorre antes da validação final.

**Prompt:**

> Execute a R15 antes de integrar em main. Apresente o inventário do que manter, remover da entrega ou ignorar. Preserve fontes técnicas, dados, histórico e branches; confira referências e não apague pastas locais sem verificar seu conteúdo.

### R16 — Validação da entrega e integração

**Recorte:** árvore limpa candidata a entrega, notebook, ambiente recriado, PRs e main.

**Revisão:** instalar a partir do requirements em ambiente isolado e executar o notebook do início ao fim com kernel limpo e diretório documentado. Resolver falhas e warnings relevantes. Comparar tabelas, matrizes e texto com as saídas produzidas; salvar resultados. Inspecionar apresentação renderizada, incluindo legibilidade dos quatro grupos de gráficos, tabelas e fórmulas.

Conferir diff do PR, matriz de requisitos e fontes depois da limpeza. Integrar a P10 revisada em develop e a entrega limpa em main; preservar branches. Confirmar commit e árvore exata de main. Mudanças após essa conferência exigem revalidar o que afetarem.

Verificar visibilidade pública e situação do vídeo/AVA separadamente. A publicação e a submissão não são realizadas por este roteiro. Respeitar o bloqueio de alterações após entrega até a nota. O lembrete de ensino avançado já está registrado; retomá-lo quando o projeto realmente for encerrado, sem criar duplicata.

**Aceite:** execução limpa comprovada, saídas inspecionadas, README reproduzido, rubricagem rastreável e main limpa. Pendências externas explicitadas; nenhuma afirmação de “100% entregue” com vídeo, visibilidade ou AVA desconhecidos.

**Prompt:**

> Execute a R16 somente após a limpeza. Valide o notebook e o ambiente da entrega, confira requisitos e apresentação e revise o PR antes da integração. Informe o commit final e diferencie conclusão técnica das pendências externas.

## 6. Constatações preparatórias que direcionam a revisão

| Local | Constatação na referência remota | Encaminhamento |
| --- | --- | --- |
| Abertura | Dois parágrafos usam futuro; Bruno informou alteração local | Conferir na R00; não repetir automaticamente. |
| Imports e prints | Caminho pessoal e separadores decorativos; faltam métricas da ampliação remota | R01: reduzir ruído e conferir imports locais. |
| Duplicidades | Diagnóstico presente; drop_duplicates não aparece | R04: implementar operação explícita com zero remoções esperado. |
| Estatísticas por tipo | Evidência da decisão global, com tabela extensa | R05: manter evidência suficiente e resumir se necessário. |
| Potência | Fórmula coerente; saída longa e precisão excessiva | R06: apresentação mais compacta. |
| Dummies | Testa igualdade e ordem das colunas, mas print fala só em número | R07: corrigir descrição da verificação. |
| Reamostragem | Razão explicada; perda expressiva pouco quantificada | R07: explicitar impacto sem trocar técnica. |
| Experimentos | Baseline e consulta ao teste repetidos em várias interpretações | R09–R12: centralizar ressalvas sem perder visibilidade. |
| Avaliação | Remoto contém só acurácia; conversa já contém métricas por classe | R00/R11: revisar a versão local e a ordem das novas células. |
| Consolidação local | Identidade derivada de strings dos nomes | R11: verificar correspondência, unicidade e ausência de nulos. |
| Fontes | Notebook depende de links dentro de docs | R15: preservar fontes técnicas ou atualizar links. |
| README e requisitos | README só com título; requirements ausente | R14: construir documentação de execução e ambiente. |
| Ignore | Não cobre os dois diretórios temporários vistos no status local | R15: avaliar conteúdo e regras específicas. |

São constatações de preparação, não a aprovação definitiva de cada fase.

## 7. Referências numéricas para reconciliação

### Experimentos da P09

| Modelo | Parâmetro | Acurácia treino reamostrado | Acurácia teste |
| --- | --- | ---: | ---: |
| KNN | K=3 | 94,17% | 93,60% |
| KNN | K=5 | 93,36% | 94,90% |
| KNN | K=7 | 92,62% | 95,10% |
| Árvore | profundidade 3 | 91,00% | 96,40% |
| Árvore | profundidade 5 | 95,50% | 94,20% |
| Árvore | sem limite | 99,85% | 94,40% |

### Diagnóstico apresentado por Bruno na conversa

| Modelo | TN | FP | FN | TP | Alertas | Acurácia | Precisão de falha | Recall de falha |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| KNN, K=7 | 1.853 | 79 | 19 | 49 | 128 | 95,10% | 38,28% | 72,06% |
| Árvore, profundidade 3 | 1.892 | 40 | 32 | 36 | 76 | 96,40% | 47,37% | 52,94% |

Total de teste: 2.000; normais: 1.932; falhas: 68. Baseline normal: 1.932/2.000 = 96,60% de acurácia, zero recall e precisão indefinida por ausência de alertas.

A árvore ganha 1,30 ponto percentual de acurácia. O KNN detecta 13 falhas adicionais e emite 39 alertas falsos adicionais. Essas diferenças são observadas neste teste; não estabelecem sozinhas o melhor custo operacional.

Se a execução final divergir, investigar dados, versões, ordem, semente e transformações. Não ajustar outputs ou conclusões manualmente para reproduzir esta tabela.

## 8. Política de arquivos da entrega

| Tipo | Destino esperado antes de main |
| --- | --- |
| notebooks/manutencao_preditiva.ipynb | Manter como único notebook principal, com saídas finais. |
| data/manutencao_preditiva.csv | Manter íntegro como entrada original. |
| README.md, requirements.txt e .gitignore | Manter e validar. |
| docs/enunciado-projeto.md e anotações da engenharia | Manter se usados como fontes da solução; são documentos técnicos pertinentes. Revisar links se reorganizados. |
| docs/continuidade.md, este roteiro e outros registros de interação | Retirar da árvore candidata a main; permanecerão no histórico/branch de planejamento. |
| Notebooks de ensaio, cópias numeradas, scripts e prévias de revisão | Retirar da entrega quando não forem necessários à execução ou documentação. |
| Checkpoints, caches, ambientes, arquivos temporários de Jupyter | Ignorar; retirar do versionamento se estiverem rastreados. |
| .virtual_documents/ e anaconda_projects/ observados localmente | Inspecionar antes; ignorar conteúdo temporário pertinente ao projeto, sem apagar outros trabalhos. |
| Branches e histórico Git | Preservar; limpeza da árvore final não implica eliminação do histórico. |

A árvore mínima final deve conter notebook, dados, ambiente, README e somente fontes/documentos técnicos necessários. Não criar novas pastas apenas para preencher uma estrutura.

Este roteiro será mantido numa branch de planejamento, separado da branch local de implementação. Não será integrado em main. Se for copiado temporariamente para a branch da P10, deverá ser removido na R15.

## 9. Referências técnicas oficiais

Consultadas na preparação; servem como apoio à revisão, sem substituir o enunciado:

- [Boas práticas e vazamento de dados — scikit-learn](https://scikit-learn.org/stable/common_pitfalls.html).
- [Separação de avaliação e seleção — scikit-learn](https://scikit-learn.org/stable/modules/cross_validation.html).
- [StandardScaler — scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html).
- [RandomUnderSampler — imbalanced-learn](https://imbalanced-learn.org/stable/references/generated/imblearn.under_sampling.RandomUnderSampler.html).
- [confusion_matrix — scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.confusion_matrix.html).
- [precision_score — scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_score.html).
- [recall_score — scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.recall_score.html).

## 10. Registro de progresso

| Etapa | Situação | Evidência de encerramento |
| --- | --- | --- |
| R00 | Concluída | Anexo manutencao_preditiva(4).ipynb, 13/10/2026; comparação integral com P09. |
| R01 | Pendente | — |
| R02 | Pendente | — |
| R03 | Pendente | — |
| R04 | Pendente | — |
| R05 | Pendente | — |
| R06 | Pendente | — |
| R07 | Pendente | — |
| R08 | Pendente | — |
| R09 | Pendente | — |
| R10 | Pendente | — |
| R11 | Pendente | — |
| R12 | Pendente | — |
| R13 | Pendente | — |
| R14 | Pendente | — |
| R15 | Pendente | — |
| R16 | Pendente | — |

Em cada encerramento, registrar de forma curta a versão revisada, mudanças materiais, verificações e próxima etapa. A simples aplicação de uma instrução não constitui aceite sem conferir sua evidência.

### Encerramento da R00 — 13/10/2026

Versão de trabalho: anexo **manutencao_preditiva(4).ipynb**, enviado por Bruno na conversa. SHA-256: **5b35e9bcaba6140a507b81f6ad89364074ae0e2fed0d2be70a3753d1fab67bfd**. Origem informada pelo terminal: branch local docs/p10-entrega-final; notebook é o único arquivo rastreado modificado, com 29 inserções e duas exclusões. Pastas não rastreadas: .virtual_documents/ e anaconda_projects/, reservadas à R15.

Comparação com o notebook da P09 no commit f0c2b9051f6687a8d41a7a75cc1822b7ae3e4db5: 58 para 59 células; 30 para 31 células de código. Exatamente uma célula existente foi modificada — introdução com tempo verbal atualizado — e uma célula foi acrescentada — previsões e matrizes. As outras 57 células preservam seu código/texto; nenhuma foi removida.

A nova célula de matrizes tem execution_count nulo e nenhuma saída salva. Usa confusion_matrix, mas o import dessa função não aparece no arquivo. Precisão, recall, tabela consolidada e veredito ampliado apresentados/discutidos na conversa não estão neste anexo. O veredito continua sendo o da P09. A operação drop_duplicates também permanece ausente.

As 30 células anteriores têm contadores 1–30 e nenhuma saída de erro salva. Isso não comprova execução integral da versão ampliada em kernel limpo. Nesta etapa foram inspecionados conteúdo, ordem, diferenças e metadados; o notebook não foi executado novamente nem alterado.

Usar o anexo como fonte da implementação atual e conservar os resultados da conversa apenas como referências a reconciliar. Conferir imports na R01; deduplicação na R04; recuperar a avaliação complementar na R11; atualizar o veredito na R12. Não repetir a correção da introdução já aplicada. Próxima etapa: R01.
