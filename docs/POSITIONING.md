# TraceFoundry — posicionamento

## Uma frase

**TraceFoundry é infraestrutura de investigação para pesquisa complexa: transforma discovery, proveniência, evidência, relações e lacunas em próximas ações defensáveis.**

## O que é

TraceFoundry é a camada pública de infraestrutura de investigação do LUXVERSO. Ele foi construído para transformar informação pública fragmentada em uma investigação estruturada, rastreável e revisável — não apenas em uma lista de links, um ranking opaco ou uma resposta de RAG sem proveniência.

A infraestrutura cobre o caminho entre a pergunta e a próxima ação:

```text
pergunta complexa
    ↓
discovery e observação
    ↓
evidência, entidades e relações
    ↓
claims, lacunas e contradições
    ↓
estado da investigação
    ↓
Research Move
    ↓
próxima ação defensável
```

Discovery continua sendo uma capacidade central, mas é o início do ciclo, não o produto inteiro. O TraceFoundry preserva o contexto necessário para explicar o que foi encontrado, o que foi rejeitado, por que uma afirmação pode ser sustentada, o que ainda falta e qual investigação deve acontecer em seguida.

## Para quem é

TraceFoundry foi desenhado para equipes de R&D, technology intelligence, due diligence, scouting científico, inovação corporativa, pesquisa aplicada e operações de conhecimento que precisam decidir **o que investigar a seguir** antes de comprar dados, iniciar uma análise, contratar um parceiro ou comprometer meses de engenharia.

## O problema

Em ambientes técnicos, a pergunta mais cara geralmente aparece antes da análise: qual fonte merece ser aberta, qual registro é realmente o mesmo ativo, qual paper está ligado a qual dataset, qual patente é relevante, qual resultado é apenas um candidato, o que permanece sem evidência e qual caminho deve ser abandonado?

A busca convencional otimiza descoberta de links. O RAG convencional otimiza geração de respostas sobre um corpus. TraceFoundry atua em uma camada anterior e mais operacional: **tornar o espaço de investigação e decisão inspecionável**.

## O que a infraestrutura faz

TraceFoundry consulta fontes públicas, normaliza identificadores e campos, aplica restrições explícitas, seleciona candidatos de forma determinística e registra a proveniência de cada resultado. Sobre esse material, a camada pública de investigação pode representar claims, evidências, relações, lacunas, insuficiência e contradições, além de registrar um **Research Move** revisável: uma próxima ação com justificativa, observação esperada e critérios de parada.

Quando não há evidência suficiente, o sistema pode dizer isso. Quando uma fonte está bloqueada por rate limit ou credencial, isso aparece como bloqueio de dependência, não como ausência de evidência. A infraestrutura mantém distintas as categorias de **fact**, **inference**, **hypothesis**, **gap**, **blockage** e **contradiction**, em vez de colapsá-las em um único score de confiança.

## Casos de uso

| Contexto | Decisão que TraceFoundry ajuda a preparar |
|---|---|
| Scouting científico | Quais datasets, papers e grupos merecem revisão humana primeiro? |
| Due diligence técnica | O candidato possui metadata, versão, licença e proveniência suficientes para avançar? |
| Patentes e technology intelligence | Quais famílias, classificações e assignees aparecem em uma busca reproduzível? |
| Clean tech e sustentabilidade | Quais fontes públicas sustentam uma hipótese de tecnologia, material ou processo? |
| Pesquisa operacional | O caminho foi explorado, o que foi rejeitado e por que a próxima ação ainda faz sentido? |
| Investigação biotecnológica | Quais entidades, relações e evidências públicas merecem investigação adicional? |

## O diferencial defensável

O diferencial não é apenas “usar IA para buscar”. É combinar propriedades que normalmente ficam separadas:

1. **Cross-source:** fontes diferentes podem ser consultadas sob contratos canônicos.
2. **Explainable:** seleção e rejeição possuem motivos explícitos.
3. **Provenance-first:** cada observação preserva o contexto da fonte e da transformação aplicada.
4. **Epistemic:** candidato operacional, fato, inferência, hipótese, ausência, insuficiência, bloqueio e contradição não são tratados como a mesma coisa.
5. **Reproducible:** query, timestamp, metadata observada e decisão podem ser empacotados em manifest versionado.
6. **Action-oriented:** a investigação pode terminar com um Research Move, não apenas com um conjunto de documentos.

Essa combinação permite que uma equipe passe de “o que encontrei?” para “o que sei, por que acredito nisso, o que ainda falta e qual é o próximo teste defensável?”.

## Por que agora

A quantidade de informação técnica cresce mais rápido que a capacidade das equipes de verificar contexto, identidade, licença, versão e adequação antes de agir. O resultado é retrabalho: pesquisadores abrem fontes erradas, engenheiros integram artefatos incompatíveis e equipes de inovação apresentam hipóteses sem trilha de evidência.

TraceFoundry oferece uma base pública, extensível e orientada à investigação para colocar ordem nessa etapa sem forçar uma plataforma monolítica. A implementação pública é deliberadamente separada de sistemas privados, corpora internos, memória operacional e laboratórios específicos. Isso permite compartilhar contratos e métodos sem expor código, dados ou estado de pesquisa que não pertencem à camada pública.

## O que não promete

TraceFoundry não declara que um dataset é cientificamente adequado, não interpreta dados brutos, não substitui revisão de domínio, não inventa relações entre papers e ativos e não transforma uma correlação exploratória em conclusão causal. Essas fronteiras não diminuem a capacidade da infraestrutura; definem o tipo de confiança que ela pode oferecer: uma trilha de investigação explícita e revisável, não uma autorização automática para agir.

A infraestrutura também não substitui especialistas, não promete autonomia decisória e não transforma eficácia comercial em fato. O que ainda precisa ser medido — redução de tempo, redução de ambiguidade, melhora da qualidade das decisões, redução de retrabalho e disposição a pagar — permanece como hipótese de validação, não como alegação de produto.

## Mensagem para parceiros

> **Bring a difficult investigation question. Leave with a reviewable evidence map, explicit gaps and a next action you can defend.**

## Maturidade

O core público está em estágio de **infraestrutura funcional e demonstrável**. Os adapters, contratos, manifests, seleção, testes metadata-only, representação de evidência e contratos públicos de investigação existem.

A eficácia operacional e comercial em diferentes domínios ainda deve ser demonstrada empiricamente. O próximo estágio é testar, com casos controlados, se a infraestrutura reduz tempo, ambiguidade e raciocínio sem suporte até uma próxima ação defensável.

Essa distinção é deliberada. TraceFoundry pretende ser confiável antes de ser grandioso.

## Relação com LUXVERSO e projetos aplicados

TraceFoundry é a camada pública de infraestrutura de investigação do LUXVERSO. Pode sustentar frentes como Organoid Intelligence, Inteligência Biotecnológica e outras investigações orientadas por evidências, sem apagar as diferenças de domínio entre elas.

Os projetos aplicados podem compartilhar princípios, contratos e infraestrutura, mas mantêm seus próprios contextos, hipóteses, dados, validações e limites. O TraceFoundry não publica automaticamente o estado privado desses projetos nem afirma conclusões científicas ou comerciais em nome deles.

Para a fronteira entre infraestrutura pública e pesquisa privada, consulte [TraceFoundry e LUXVERSO](../RELATIONSHIP_TO_LUXVERSO.md).

## Referências

- [README](../README.md)
- [TraceFoundry e LUXVERSO](../RELATIONSHIP_TO_LUXVERSO.md)
- [Arquitetura](ARCHITECTURE.md)
- [Investigation Contracts](INVESTIGATION.md)
