# Atividade 2: Organização da Qualidade no LocalEats

## Tarefa 1: Diagnóstico da situação

| Problema identificado | Possível consequência para o produto ou para a equipe |
| :--- | :--- |
| Funcionalidades chegam aos usuários com defeitos. | Diminui a confiança do cliente no produto, gera avaliações negativas e aumenta significativamente o custo de manutenção com retrabalho constante. |
| Alguns integrantes acreditam que somente o QA deve testar. | Sobrecarga do profissional de QA, criando um problema no final do ciclo de desenvolvimento. Isso atrasa os lançamentos, tornando a correção de bugs muito mais complicada, pois são descobertos tarde demais. |
| Não está claro quem pode aprovar a disponibilização de uma nova versão. | Lançamentos caóticos e arriscados. Versões podem ir para produção sem a devida validação de negócio, ou o lançamento pode atrasar porque ninguém assume a responsabilidade de aprovar o resultado final. |

**A qualidade do LocalEats deve ser responsabilidade exclusiva do profissional de QA? Justifiquem.**

Não. A qualidade deve ser uma responsabilidade compartilhada por toda a equipe. Se apenas o QA testa no final do ciclo, os defeitos se tornam mais caros e demorados para corrigir. Desenvolvedores devem garantir a qualidade do código e Product Owners (POs) devem garantir a qualidade dos requisitos, deixando o QA atuar de forma estratégica na prevenção de riscos e testes complexos.

## Tarefa 2: Papéis e competências

| Integrante | Papel analisado | Responsabilidades relacionadas à qualidade | Competências técnicas | Competências comportamentais |
| :--- | :--- | :--- | :--- | :--- |
| Brian da Silva Guterres | Desenvolvedor | Garantir que o código atenda aos critérios de aceitação; criar e executar testes unitários antes de repassar a tarefa; realizar revisão de código dos colegas para identificar falhas lógicas precocemente. | Domínio da linguagem/framework do projeto; conhecimento em ferramentas de versionamento, como Git; habilidade com frameworks de testes unitários; conhecimento em boas práticas (Clean Code). | Atenção aos detalhes; colaboração para trabalhar em equipe nas revisões de código; pensamento crítico para antecipar cenários de falha; comunicação clara para alinhar dúvidas de requisitos. |

## Tarefa 3: Matriz de responsabilidades (RACI)

| Atividade de qualidade | Product Owner (PO) | Desenvolvedor | QA | Liderança Técnica |
| :--- | :---: | :---: | :---: | :---: |
| Definir critérios de aceitação | R, A | C | C | I |
| Revisar requisitos | A | C | R | C |
| Implementar a funcionalidade | I | R, A | I | C |
| Revisar o código | I | R | I | A |
| Criar testes unitários | I | R, A | I | C |
| Planejar e executar testes do sistema | I | I | R, A | I |
| Registrar e acompanhar defeitos | C | R | R | A |
| Priorizar a correção dos defeitos | R, A | I | C | C |
| Aprovar a disponibilização da versão | A | I | C | R |

### Lacuna ou conflito encontrado

Nota-se que a atividade "Planejar e executar testes do sistema" ficou concentrada unicamente no papel do QA (como Responsável e Aprovador). Embora faça sentido técnico, isso gera um conflito: se o volume de entregas dos desenvolvedores for alto, o QA não dará conta de testar tudo sozinho, atrasando a disponibilização das versões e gerando os defeitos em produção relatados no cenário do LocalEats.

## Práticas recomendadas

| Prática recomendada | Problema que ajuda a resolver | Papéis envolvidos |
| :--- | :--- | :--- |
| Definição de Pronto Formalizada | Resolve o problema "não está claro quem pode aprovar a disponibilização". Criação um checklist obrigatório onde fica oficializado que a versão só sobe após o "Aprovado" do PO. | Product Owner, Desenvolvedor, QA, Liderança Técnica |
| Testes em Pares / Shift-Left | Resolve o problema de "somente o QA deve testar". Ao colocar um Dev e um QA para planejarem testes juntos precocemente, a equipe previne defeitos antes da implementação, dividindo a carga de trabalho. | Desenvolvedor, QA |

## Uso de inteligência artificial

**Ferramenta utilizada:**
Gemini

**Como foi utilizada:**
Utilizada para melhorar estruturas de texto, elaboração de ideias, correções ortográficas e matriz de responsabilidades.

**Como as respostas foram verificadas:**
Todas foram revisadas e refeitas de acordo com a vontade do grupo e o que foi pedido nas instruções do trabalho.
