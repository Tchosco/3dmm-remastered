# M0 — Fundação do Movie Studio Web

**Status:** IN PROGRESS

## Objetivo

Estabelecer um baseline técnico, legal e operacional confiável para evoluir o fork `Tchosco/3dmm-remastered` em uma plataforma própria de produção audiovisual baseada em navegador, provisoriamente chamada **Movie Studio Web**.

A M0 não adiciona funcionalidades de produto. Seu papel é auditar, estabilizar, documentar e preparar a base antes da transformação funcional.

## Upstream

- Projeto de origem: `Phantomcrew-de/3dmm-remastered`
- Fork de trabalho: `Tchosco/3dmm-remastered`
- Licença do código: MIT, preservando os avisos de copyright e licença existentes.
- Assets proprietários do Microsoft 3D Movie Maker não fazem parte do produto próprio e não devem ser redistribuídos como assets do Movie Studio Web.

## Princípios da M0

1. Preservar a `main` como baseline estável até fechamento do gate.
2. Trabalhar em branch dedicada por milestone/submilestone.
3. Não iniciar M1 antes de M0 estar concluída e aprovada no gate humano.
4. Não misturar nesta fase backend, autenticação, colaboração online ou IA.
5. Não substituir ou remover atribuições/licenças do upstream.
6. Preferir assets próprios ou com licença compatível em qualquer teste que pretenda virar baseline do projeto próprio.

## Submilestones

### M0.1 — Baseline, identidade e inventário

**Status:** IN PROGRESS

- confirmar que o fork corresponde ao upstream escolhido;
- registrar licença, proveniência e limites de uso de assets;
- registrar estrutura do repositório;
- executar o editor localmente sem alterações funcionais;
- inventariar capacidades já existentes;
- registrar requisitos de execução e limitações conhecidas;
- definir o nome provisório Movie Studio Web somente em documentação, sem rebranding funcional nesta etapa.

### M0.2 — Auditoria funcional

**Status:** PLANNED

Auditar, sem ampliar escopo, os sistemas existentes de personagens, animações, timeline, áudio, backgrounds/depth, lipsync, takes, projetos, importação e exportação.

### M0.3 — Auditoria arquitetural

**Status:** PLANNED

Mapear módulos, responsabilidades, dependências, pontos de acoplamento e riscos do atual editor, incluindo o grande `3dmm-editor-main.mjs`.

### M0.4 — Baseline audiovisual legalmente reutilizável

**Status:** PLANNED

Validar um ciclo mínimo com assets próprios ou compatíveis: editar → salvar → carregar → reproduzir → exportar.

### M0.5 — Preparação de staging

**Status:** PLANNED

Preparar documentação e configuração para execução em VPS sem introduzir autenticação, co-op ou backend de produto.

### M0.6 — Staging VPS e gate humano

**Status:** PLANNED

Publicar o baseline em ambiente de staging, validar carregamento, reprodução, persistência de projeto e comportamento após reload, e realizar o gate humano final da M0.

## Fora de escopo da M0

- co-op/multiplayer;
- contas e autenticação;
- banco de dados de produção;
- IA de direção;
- editor de roteiro;
- multicâmera avançada;
- biblioteca online de assets;
- mudanças amplas de UX;
- reescrita da engine;
- novos formatos de personagem;
- funcionalidades comerciais.

## Critérios de aceite da M0

A M0 só poderá ser marcada como `DONE` quando:

- todas as submilestones M0.1–M0.6 estiverem concluídas;
- o baseline estiver documentado;
- testes definidos estiverem aprovados;
- não houver falhas críticas/altas conhecidas no escopo validado;
- a documentação de licença/proveniência estiver preservada;
- o staging VPS estiver funcional;
- o gate humano tiver sido executado e aprovado;
- a `main` só receber a milestone após aprovação.

## Estratégia Git

Fluxo pretendido:

`implementação/auditoria local → testes → commit na branch da milestone → staging → gate humano → merge --no-ff na main`

Evitar squash/rebase no fechamento da milestone para preservar o histórico de desenvolvimento.

## Próximo gate

Concluir M0.1 antes de iniciar qualquer item da M0.2.
