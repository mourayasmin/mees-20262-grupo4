# Mapeamento Sistemático: Agentes Socráticos baseados em LLM

Mapeamento sistemático, seguindo Petersen et al. (2008; 2015), das técnicas de design que mantêm agentes tutores baseados em LLM no modo socrático.

**Status:** protocolo, estratégia de busca e critérios de seleção definidos.
**Equipe:** 4 pesquisadores (A, B, C, D) – UFG
**Entrega da versão inicial do artigo:** 12/10/2026

---

## Sumário

1. [Contexto e justificativa](#1-contexto-e-justificativa)
2. [Objetivo](#2-objetivo)
3. [Questões de pesquisa](#3-questões-de-pesquisa)
4. [Escopo e decisões gerais](#4-escopo-e-decisões-gerais)
5. [Estratégia de busca](#5-estratégia-de-busca)
6. [Critérios de inclusão e exclusão](#6-critérios-de-inclusão-e-exclusão)
7. [Processo de seleção](#7-processo-de-seleção)
8. [Extração de dados](#8-extração-de-dados)
9. [Cronograma](#9-cronograma)
10. [Pendências](#10-pendências)
11. [Referências metodológicas](#11-referências-metodológicas)

---

## 1. Contexto e justificativa

LLMs são cada vez mais usados como tutores, mas tendem a fornecer respostas diretas, o que pode prejudicar a aprendizagem. Agentes socráticos guiam o raciocínio do aluno por perguntas orientadoras, alinhados a teorias como a Zona de Desenvolvimento Proximal (Vygotsky) e a Taxonomia de Bloom.

As técnicas que sustentam esse comportamento (memória, raciocínio, controle de estado e resistência à pressão do aluno) estão dispersas na literatura e ainda não foram mapeadas sistematicamente.

## 2. Objetivo

No formato GQM: **analisar** estudos primários sobre agentes tutores baseados em LLM, **com o propósito de** caracterizar as técnicas de design que sustentam o comportamento socrático, **do ponto de vista de** pesquisadores e desenvolvedores de tecnologia educacional, **no contexto da** educação formal e informal.

## 3. Questões de pesquisa

| ID | Tema | Questão |
|---|---|---|
| RQ1 | Indução do comportamento socrático | Quais estratégias (engenharia de prompt, personas, few-shot, fine-tuning, RLHF/DPO) induzem agentes baseados em LLM a guiar o aluno por perguntas em vez de dar respostas diretas? |
| RQ2 | Memória, raciocínio e controle de estado | Quais técnicas de memória (diálogo, modelo do aluno), raciocínio (chain-of-thought, monólogo interno) e controle de estado (máquinas de estado, escadas de dicas) são usadas para regular o suporte e evitar a revelação prematura da resposta? |
| RQ3 | Resistência à pressão do aluno | Como os agentes detectam e respondem a tentativas do aluno de obter a resposta pronta (pedidos insistentes, frustração, jailbreak)? |

## 4. Escopo e decisões gerais

| Decisão | Definição |
|---|---|
| Período | 2022 até a data de corte da busca (03/10/2026) |
| Idiomas | Inglês e português |
| Literatura cinzenta | Incluída (ex.: arXiv), sinalizada no formulário e analisada à parte. Se houver versão revisada por pares, usar a publicada. |
| Equipe | 4 revisores, triagem em duplas (A+B e C+D) |
| Concordância | Kappa de Fleiss no piloto; ≥ 0,6 aceitável |
| Ferramentas | Rayyan (triagem), Zotero (referências), planilha compartilhada (registro da busca) |
| Acesso | Portal CAPES via CAFe/VPN da UFG |

## 5. Estratégia de busca

Os termos foram derivados via PICO:
- **P (população):** contextos educacionais (implícito)
- **I (intervenção):** agentes/tutores baseados em LLM
- **C (comparação):** não se aplica
- **O (resultado):** comportamento socrático e scaffolding

A busca é aplicada em título, resumo e palavras-chave.

### String em inglês

```
("large language model*" OR LLM* OR "generative AI" OR GPT* OR ChatGPT
 OR "conversational agent*")
AND
(tutor* OR "pedagogical agent*" OR "teaching assistant*"
 OR "educational chatbot*")
AND
(Socratic OR scaffold* OR "guided question*" OR "guiding question*"
 OR guardrail* OR "answer leak*" OR "withhold* answer*"
 OR "pedagogical alignment" OR "productive struggle")
```

### String em português

```
("modelo* de linguagem" OR LLM OR "IA generativa" OR ChatGPT)
AND (tutor* OR "agente* pedagógico*" OR chatbot*)
AND (socrátic* OR andaime* OR scaffolding OR "pergunta* orientadora*")
```

### Bases e responsáveis (busca em 03/10/2026)

| Base | Responsável | Observação |
|---|---|---|
| Scopus | A | Maior cobertura multidisciplinar |
| ACM DL | B | Educação em computação (SIGCSE, L@S) |
| IEEE Xplore | B | Engenharia e educação (FIE, ICALT) |
| ACL Anthology | C | Trabalhos de NLP (ACL, EMNLP, BEA); busca limitada, registrar adaptação |
| arXiv | C | Literatura cinzenta |
| SBC OpenLib e RBIE | D | Estudos em português (SBIE, WIE); string em português |

### Validação com conjunto de controle (responsável: D)

A string deve recuperar pelo menos **80%** destes artigos. Se algum faltar, analisar os termos que ele usa, ajustar a string e documentar a iteração. Confirmar as referências antes de usar.

- Macina et al. (2023), *MathDial*
- Liu et al. (2024), *SocraticLM*
- Liffiton et al. (2023), *CodeHelp*
- Bastani et al. (2024), *Generative AI Can Harm Learning*
- Wang et al. (2024), *Bridging the Novice-Expert Gap* (Bridge)
- Google (2024), relatório técnico *LearnLM*

### Registro (para o PRISMA)

Para cada base, anotar data, string exata, filtros aplicados e número de resultados. Exportar em RIS ou BibTeX, importar no Rayyan e registrar o total após remoção de duplicatas.

## 6. Critérios de inclusão e exclusão

> Critérios aprovados pela equipe em 01/10/2026; podem ser refinados no piloto de calibração, com registro da versão.

Um artigo é incluído se atende a **todos** os critérios de inclusão e a **nenhum** de exclusão.

| ID | Critério de inclusão |
|---|---|
| CI1 | Estudo primário que apresenta ou avalia um agente/tutor baseado em LLM para fins educacionais |
| CI2 | O agente busca guiar o aluno por perguntas, scaffolding ou retenção da resposta (comportamento socrático) |
| CI3 | Descreve ao menos uma técnica relacionada às RQ1–RQ3 |
| CI4 | Publicado entre 2022 e 03/10/2026 |
| CI5 | Escrito em inglês ou português |

| ID | Critério de exclusão |
|---|---|
| CE1 | Tutor ou chatbot que não usa LLM (ex.: ITS baseado em regras) |
| CE2 | LLM usado só para gerar conteúdo, corrigir ou responder, sem diálogo de tutoria |
| CE3 | Sem descrição técnica do agente (ex.: apenas questionário de percepção) |
| CE4 | Estudo secundário (revisões e mapeamentos); usado apenas no snowballing |
| CE5 | Resumo estendido, pôster, editorial, tutorial ou keynote |
| CE6 | Texto completo inacessível |
| CE7 | Duplicata ou versão anterior de estudo já incluído |

**Qualidade mínima para literatura cinzenta:** método descrito, autores identificáveis e detalhe técnico suficiente para responder a pelo menos uma RQ.

### Como os critérios foram derivados

| Origem | Critérios |
|---|---|
| Intervenção (agente baseado em LLM) | CI1, CE1 |
| Resultado (comportamento socrático / scaffolding) | CI2, CE2 |
| Conteúdo para as RQ1–RQ3 | CI3, CE3 |
| Tipo de estudo e de publicação | CE4, CE5 |
| Período, idioma, acesso e duplicidade | CI4, CI5, CE6, CE7 |
| Qualidade mínima | Critério para literatura cinzenta |

### Etapa de aplicação

- **Título e resumo:** CI1, CI2, CI4, CI5, CE1, CE2, CE4, CE5, CE7
- **Texto completo:** CI3, CE3, CE6 e a qualidade mínima para literatura cinzenta

### Regras de decisão para casos-limite (validar no piloto)

| Caso | Decisão |
|---|---|
| Chatbot educacional com LLM sem diálogo socrático explícito, mas que retém a resposta | Incluir (atende CI2) |
| Tutor que entrega a resposta após N tentativas | Incluir: há controle de suporte (RQ2) |
| Estudo só de avaliação (ex.: RCT) sem detalhe técnico do agente | Excluir por CE3 (**a definir pela equipe**) |
| Paper de dataset ou benchmark de tutoria (ex.: MathDial) | Incluir se propõe ou testa técnicas ligadas às RQs |
| Preprint com versão publicada | Manter só a versão publicada (CE7) |

### Boas práticas e calibração

- Critérios objetivos e verificáveis, sem termos vagos como "relevante".
- Para cada critério, registrar 1 exemplo de caso incluído e 1 de excluído durante o piloto.
- Divergências no piloto geram novas regras de decisão ou reescrita do critério.
- Registrar cada versão dos critérios neste protocolo (data e mudança).

## 7. Processo de seleção

A seleção é feita no Rayyan em modo cego, em duas etapas, com cada artigo avaliado por dois revisores.

1. **Preparar o Rayyan (03/10).** Criar a revisão, convidar os 4 membros, importar os arquivos de todas as bases e resolver as duplicatas. Cadastrar os rótulos de exclusão CE1–CE7 como motivos.
2. **Piloto de calibração (04/10).** Os 4 avaliam os mesmos 20–30 artigos por título e resumo.
   - Calcular o Kappa de Fleiss; meta ≥ 0,6.
   - Discutir divergências e reescrever critérios ambíguos.
   - Se o Kappa ficar abaixo de 0,6, repetir com nova amostra.
3. **Triagem por título e resumo (05–06/10).** Dividir os artigos restantes em duas metades: dupla A+B e dupla C+D.
   - Cada revisor marca *incluir*, *excluir* (com motivo) ou *talvez*.
   - Na dúvida, incluir: se um dos dois incluir ou marcar *talvez*, o artigo segue para o texto completo.
   - Conflitos de exclusão são resolvidos por um membro da outra dupla.
4. **Obter os textos completos.** Baixar via Portal CAPES e anexar no Rayyan ou no Zotero. Os inacessíveis são excluídos por CE6.
5. **Triagem por texto completo (07/10).** Mesmas duplas e regra de desempate. Aplicar todos os critérios e a qualidade mínima para literatura cinzenta. Registrar o motivo de cada exclusão.
6. **Snowballing (09/10).** Uma iteração backward nas referências dos incluídos, aplicando os mesmos critérios. Revisões excluídas por CE4 também servem de fonte.
7. **Registrar o fluxo PRISMA.** Anotar os números de cada etapa: identificados por base, após duplicatas, após título e resumo, após texto completo, adicionados pelo snowballing e total final.

## 8. Extração de dados

O formulário será testado com 5–10 artigos antes do uso completo.

| Campo | Conteúdo |
|---|---|
| Identificação | Autores, ano, título, veículo |
| Tipo de publicação | Revisado por pares ou literatura cinzenta |
| Tipo de pesquisa | Classificação de Wieringa (proposta de solução, validação, avaliação etc.) |
| Arquitetura | Agente único ou multiagente; LLM base |
| RQ1 | Estratégia de indução do comportamento socrático |
| RQ2 | Técnicas de memória, raciocínio e controle de estado |
| RQ3 | Tratamento de pressão ou jailbreak |
| Contexto | Domínio e nível de ensino |
| Avaliação | Método e métricas (ex.: vazamento de resposta) |

## 9. Cronograma

| Data | Atividade | Responsáveis |
|---|---|---|
| 01–02/10 | Protocolo, string e critérios | Todos |
| 03/10 | Busca nas bases, validação e remoção de duplicatas | A, B, C, D (ver bases) |
| 04/10 | Piloto de calibração e Kappa | Todos |
| 05–06/10 | Triagem por título e resumo | Duplas A+B e C+D |
| 07–08/10 | Texto completo e extração | Duplas A+B e C+D |
| 09/10 | Snowballing backward (1 iteração) | Duplas |
| 10/10 | Análise e mapas | Todos |
| 11–12/10 | Redação e revisão final | Todos |

Para caber no prazo, o escopo foi limitado a 6 bases e 1 iteração de snowballing. Se a busca retornar mais de ~500 artigos, a string será restringida. Essas escolhas entram nas ameaças à validade.

## 10. Pendências

- [x] Validar os critérios de inclusão e exclusão em equipe (aprovados em 01/10/2026)
- [ ] Decidir sobre estudos só de avaliação sem detalhe técnico (CE3)
- [ ] Confirmar as referências do conjunto de controle
- [ ] Criar a planilha de registro da busca
- [ ] Criar a revisão no Rayyan e convidar os membros
- [ ] Definir as categorias iniciais do esquema de classificação (keywording)

## 11. Referências metodológicas

- Petersen, K.; Feldt, R.; Mujtaba, S.; Mattsson, M. (2008). *Systematic Mapping Studies in Software Engineering*. EASE.
- Petersen, K.; Vakkalanka, S.; Kuzniarz, L. (2015). *Guidelines for conducting systematic mapping studies in software engineering: An update*. Information and Software Technology.
- Kitchenham, B.; Charters, S. (2007). *Guidelines for performing Systematic Literature Reviews in Software Engineering*. EBSE Technical Report.
- Wohlin, C. (2014). *Guidelines for snowballing in systematic literature studies and a replication in software engineering*. EASE.
- Wieringa, R. et al. (2006). *Requirements engineering paper classification and evaluation criteria*. Requirements Engineering.
