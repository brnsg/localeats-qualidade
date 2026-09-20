# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## Tarefa 1: Planejamento dos testes

### 1.1 Objetivo dos testes
Verificar se o sistema processa corretamente os termos inseridos na barra de pesquisa, garantindo que os restaurantes sejam filtrados exclusivamente por sua localização e que a interface lide adequadamente com pesquisas que não retornam resultados.

### 1.2 Escopo

| Integrante | Funcionalidade incluída | O que será verificado |
| :--- | :--- | :--- |
| Brian da Silva Guterres | Pesquisar restaurantes por localização na barra de pesquisa | A aplicação correta do filtro de texto por localidade (ex: Zona Sul) e a exibição ou ocultação dos cards na tela. |

| Funcionalidade não incluída | Justificativa |
| :--- | :--- |
| Filtrar por culinária (botões) | O foco destes testes está apenas na validação da barra de pesquisa de texto por localização, e não no uso dos botões de categorias. |

### 1.3 Abordagem

| Item | Decisão da equipe | Justificativa |
| :--- | :--- | :--- |
| Níveis de teste | Sistema | O fluxo será analisado do início ao fim através da interface gráfica, simulando a ação real do usuário final. |
| Tipos de teste | Funcional | O objetivo é verificar se as regras de busca por localização (texto) estão operando corretamente na listagem. |
| Perspectiva caixa-preta ou caixa-branca | Caixa-preta | Serão consideradas as entradas (texto digitado) e os resultados na tela, sem validação direta no código-fonte. |
| Técnicas de teste | Particionamento de Equivalência | O resultado da busca depende se o texto digitado corresponde a um grupo válido (local com resultados) ou inválido (local sem dados), cobrindo todas as saídas lógicas. |

### 1.4 Ambiente e responsabilidades

| Item | Definição |
| :--- | :--- |
| Ambiente necessário | Aplicação acessível no navegador Chrome; Conexão com a internet; Base de dados contendo restaurantes cadastrados em diferentes localizações (ex: Zona Sul, Centro, Zona Norte). |
| Responsáveis pelo planejamento | Brian da Silva Guterres |
| Responsáveis pela especificação dos casos | Brian da Silva Guterres |
| Responsáveis pela futura execução | Brian da Silva Guterres |

### 1.5 Critérios

| Critério | Definição da equipe |
| :--- | :--- |
| Entrada | Aplicação web online e banco de dados populado com a lista completa de restaurantes. |
| Saída | Casos de teste especificados e matriz de rastreabilidade finalizada. |
| Suspensão | Indisponibilidade do servidor (fora do ar) ou ausência da barra de pesquisa na interface. |

## Tarefa 2: Riscos e técnicas de teste

### 2.1 Análise dos riscos

| ID | Integrante | Funcionalidade | Risco | Consequência | Probabilidade | Impacto | Prioridade | Justificativa |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| R01 | Brian da Silva Guterres | Pesquisar restaurantes por localização | A busca não retornar dados mesmo quando o usuário digita uma localização onde existem restaurantes cadastrados (ex: Zona Sul). | Usuário não encontra estabelecimentos na sua região e abandona o app. | Baixa | Alto | Alta | Impacta diretamente o objetivo principal do app. |
| R02 | Brian da Silva Guterres | Pesquisar restaurantes por localização | Pesquisar um local que não existe na cidade e a tela ficar em branco ou carregando infinitamente sem feedback. | Frustração do usuário por falta de clareza do sistema. | Média | Médio | Média | Falha de usabilidade grave ao não informar que a lista está vazia. |

### 2.2 Aplicação da técnica

**Integrante responsável:** Brian da Silva Guterres

**Funcionalidade:** Pesquisar restaurantes por localização

**Risco relacionado:** R01 e R02

**Técnica escolhida:** Particionamento de equivalência

**Por que a técnica foi escolhida?**
Porque as tentativas de busca do usuário podem ser divididas em classes lógicas que devem gerar o mesmo comportamento, reduzindo a necessidade de testar infinitos nomes de bairros.

**Aplicação da técnica:**
* **Classe 1 (Válida com dados):** Digitar um texto que corresponde a uma localização com restaurantes cadastrados (Ex: "Zona Sul").

* **Classe 2 (Inválida sem dados):** Digitar um texto aleatório que não corresponde a nenhuma localização (Ex: "BairroInexistente123").

* **Classe 3 (Estado neutro/Limpeza):** Apagar o texto da busca e submeter para voltar a exibir todos.

**Casos derivados:**
CT01, CT02 e CT03

---

## Tarefa 3: Casos de teste e rastreabilidade

### 3.1 Especificação dos casos de teste

**CT01: Pesquisar por localização com resultados existentes**

* **Integrante responsável:** Brian da Silva Guterres

* **Funcionalidade:** Pesquisar restaurantes por localização

* **Risco ou requisito relacionado:** R01

* **Técnica utilizada:** Particionamento de Equivalência

* **Pré-condição:**
  O sistema possui pelo menos um estabelecimento com a localização "Zona Sul" cadastrada.

* **Dados de entrada:**
  Texto = Zona Sul

* **Passos:**
  1. Acessar a tela inicial do LocalEats.
  2. Localizar a barra de pesquisa.
  3. Digitar o termo "Zona Sul".
  4. Clicar no botão "Buscar".

* **Resultado esperado:**
  A lista de restaurantes é atualizada, exibindo apenas os estabelecimentos situados na Zona Sul.

---

**CT02: Pesquisar por localização sem resultados cadastrados**

* **Integrante responsável:** Brian da Silva Guterres

* **Funcionalidade:** Pesquisar restaurantes por localização

* **Risco ou requisito relacionado:** R02

* **Técnica utilizada:** Particionamento de Equivalência

* **Pré-condição:**
  O sistema está online e com a lista completa de restaurantes carregada.

* **Dados de entrada:**
  Texto = BairroInexistente123

* **Passos:**
  1. Acessar a tela inicial do LocalEats.
  2. Localizar a barra de pesquisa.
  3. Digitar o termo "BairroInexistente123".
  4. Clicar no botão "Buscar".

* **Resultado esperado:**
  A lista de restaurantes fica vazia e o sistema exibe uma mensagem amigável indicando que não há resultados para a busca no momento.

---

**CT03: Limpar busca para visualizar todos os restaurantes**

* **Integrante responsável:** Brian da Silva Guterres

* **Funcionalidade:** Pesquisar restaurantes por localização

* **Risco ou requisito relacionado:** R01

* **Técnica utilizada:** Particionamento de Equivalência

* **Pré-condição:**
  O usuário já realizou uma busca com sucesso e a lista está filtrada (ex: Zona Sul).

* **Dados de entrada:**
  Texto vazio

* **Passos:**
  1. Acessar a tela inicial com uma pesquisa ativa.
  2. Clicar na barra de pesquisa e apagar todo o texto digitado.
  3. Clicar no botão "Buscar" com o campo vazio.

* **Resultado esperado:**
  O filtro de texto é removido e o sistema volta a listar todos os restaurantes cadastrados na página inicial.

---

### 3.2 Matriz de rastreabilidade

| Integrante | Funcionalidade | Risco ou requisito | Técnica utilizada | Casos de teste |
| :--- | :--- | :--- | :--- | :--- |
| Brian da Silva Guterres | Pesquisar restaurantes por localização | R01 e R02 | Particionamento de equivalência | CT01, CT02, CT03 |

## Uso de inteligência artificial

**Ferramenta utilizada:**
Gemini

**Como foi utilizada:**
Utilizada como apoio no processo de brainstorming para mapeamento dos riscos operacionais na busca por localização e na elaboração das classes lógicas de particionamento.
Utilizada, também, para auxílio na formatação na linguagem de marcação "Markdown".

**Uma sugestão que precisou ser alterada ou rejeitada:**
A IA inicialmente sugeriu usar a barra de pesquisa para testar categorias de "Culinária" (seguindo o placeholder visual da interface). A sugestão foi rejeitada porque, ao explorar a aplicação manualmente, percebi que a regra de negócio do código restringe a barra de pesquisa exclusivamente à localização do restaurante, enquanto a culinária é filtrada através dos botões.

**Como as respostas foram verificadas:**
A funcionalidade foi testada manualmente de forma exploratória na aplicação web real para garantir que os testes propostos fossem exatos e factíveis (como a necessidade técnica de ter que clicar no botão Buscar após apagar o texto para que a lista fosse restaurada, provando a ausência de reatividade em tempo real).
