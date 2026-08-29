# TraceFoundry e LUXVERSO

## Relação em uma frase

> **TraceFoundry is the public research infrastructure layer of LUXVERSO.**
>
> **TraceFoundry é a camada pública de infraestrutura de investigação do LUXVERSO.**

## O que é o LUXVERSO

**LUXVERSO** é o ecossistema independente de Research & Build criado e conduzido por Vinícius Buri Lux. Ele conecta autoria, perguntas, métodos, infraestrutura, projetos, memória de investigação e evidências públicas.

**Research & Build** não é uma marca concorrente. É o modo de operação do ecossistema: entender, representar, projetar, construir, testar e aplicar.

## O que é o TraceFoundry hoje

TraceFoundry é a camada pública de infraestrutura de investigação do LUXVERSO. Seu foco é transformar informação pública fragmentada em um espaço de investigação estruturado, rastreável e revisável.

A infraestrutura conecta fontes e observações, normaliza entidades e metadados, preserva proveniência, aplica critérios explícitos, representa evidências, claims, relações, lacunas e contradições, registra decisões de seleção e rejeição e ajuda a explicitar o próximo **Research Move**: uma ação investigativa justificável, com observação esperada e critérios de parada.

A evolução pode ser resumida assim:

```text
discovery
    ↓
evidence
    ↓
claims and relationships
    ↓
gaps, insufficiency and contradiction
    ↓
investigation state
    ↓
research move
    ↓
next defensible action
```

Discovery continua sendo uma capacidade importante, mas não é mais a definição completa do projeto. O valor do TraceFoundry está em manter visível o caminho entre o que foi encontrado, o que foi observado, o que pode ser afirmado, o que permanece incerto e o que deve ser investigado a seguir.

O projeto mantém identidade própria, documentação técnica, licença e roadmap próprios. Sua autonomia técnica é parte do valor que oferece ao ecossistema e a usuários externos.

## Como a relação surgiu

TraceFoundry materializa uma necessidade recorrente nas investigações do LUXVERSO: não basta encontrar informação; é necessário saber de onde ela veio, qual transformação sofreu, por que foi considerada elegível, que relações podem ser sustentadas, o que permanece ausente e qual próximo passo pode ser defendido.

O TraceFoundry começou como uma camada de discovery associada à investigação de Organoid Intelligence e evoluiu para uma infraestrutura geral de evidence, provenance e investigation. Essa trajetória não é apagada: ela mostra como uma necessidade concreta de discovery com proveniência se tornou uma arquitetura mais geral para investigação complexa.

A arquitetura pública foi separada do laboratório privado para tornar contratos, métodos e demonstrações auditáveis sem expor memória, dados restritos, heurísticas operacionais, código proprietário ou decisões internas. O repositório público documenta a camada reutilizável; não pretende reproduzir a implementação completa de cada laboratório ou domínio aplicado.

## O que é público

O repositório público inclui contratos de investigação, adaptadores de metadados, seleção explicável, evidência negativa, manifests reproduzíveis, fixtures públicos, testes, documentação metodológica e exemplos de integração. O núcleo público opera com uma política **metadata-only por padrão**: não baixa datasets científicos nem interpreta automaticamente sua validade biológica ou técnica.

A camada pública pode ser reutilizada em discovery científico, R&D scouting, due diligence, technology intelligence, patent landscape, investigação biotecnológica, inteligência territorial e exploração de produtos orientada por evidências. O domínio pode mudar; a disciplina permanece: proveniência, evidência, relações, incerteza e próxima ação.

## O que permanece privado

Não fazem parte deste repositório memória privada, prompts privados, estados adaptativos, traces, credenciais, dados brutos ou restritos, decisões não publicadas, heurísticas operacionais privadas, corpus interno ou a implementação completa de laboratórios específicos.

Essa fronteira não é uma limitação acidental. Ela protege pessoas, fontes, propriedade intelectual e a distinção entre demonstração pública, infraestrutura reutilizável e operação de laboratório. A existência de uma arquitetura pública não implica que os sistemas privados, seus dados ou seu código sejam publicados.

## Relação com LuxMemory

LuxMemory corresponde, na arquitetura do LUXVERSO, à camada privada de memória, continuidade e estado de investigação. TraceFoundry pode produzir um manifest ou um link de revisão para uma memória privada sem gravar automaticamente em seu banco de dados.

A promoção é seletiva: trabalho privado pode gerar candidatos; um artefato público só deve ser publicado depois de revisão de proveniência, licença, segurança, reprodutibilidade e linguagem epistemológica. TraceFoundry não expõe nem substitui LuxMemory.

## Relação com os projetos

O mesmo núcleo pode sustentar frentes diferentes sem apagar suas diferenças de domínio. Organoid Intelligence usa a disciplina de evidência e limites para investigar sistemas neurais biológicos. Inteligência Biotecnológica organiza fontes, relações e achados em biotecnologia. GhostWorks e projetos de dados públicos aplicam a mesma preocupação com sinais, proveniência e decisão a outros contextos.

Esses projetos não são automaticamente equivalentes nem constituem uma única conclusão científica. Eles são aplicações e registros que podem compartilhar infraestrutura, contratos e princípios de investigação. O TraceFoundry fornece a camada pública de método e representação; cada projeto aplicado mantém seu próprio contexto, hipóteses, validações e limites.

## O que o TraceFoundry não afirma

TraceFoundry não prova, sozinho, qualidade de dados, relevância biológica, validade estatística, novidade patentária, liberdade de operação, eficácia, viabilidade comercial ou adequação a uma hipótese específica. Ele torna o caminho até uma decisão mais explícito, revisável e difícil de superestimar.

> **TraceFoundry does not replace expert judgment. It makes expert judgment faster to start, easier to audit and harder to accidentally overstate.**

## Navegação

- [LUXVERSO](https://github.com/viniburilux/LuxVerso)
- [Perfil de Vinícius Buri Lux](https://github.com/viniburilux)
- [Organoid Intelligence](https://github.com/viniburilux/organoid-intelligence)
- [Inteligência Biotecnológica](https://github.com/viniburilux/inteligencia-biotecnologica)
- [Página autoral](https://viniburilux.github.io/)

## Status

Este documento descreve a relação editorial e arquitetural entre os projetos. Ele não expõe conteúdo privado nem transforma relações de trabalho em alegações de integração técnica que não estejam documentadas no código público.

A camada pública é intencionalmente menor que o conjunto de sistemas, operações e pesquisas que pode apoiar. Essa separação permite que o TraceFoundry evolua como infraestrutura aberta de investigação sem publicar código, memória ou estado operacional privado.

## Referências

- [README](README.md)
- [Arquitetura](docs/ARCHITECTURE.md)
- [Investigation Contracts](docs/INVESTIGATION.md)
- [LUXVERSO](https://github.com/viniburilux/LuxVerso)
