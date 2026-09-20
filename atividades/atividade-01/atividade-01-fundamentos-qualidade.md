# Atividade 1: Fundamentos e Características da Qualidade no LocalEats

## 1. Identificação

**Turma:** Qualidade de Software  
**Estudante:** Brian da Silva Guterres

**Data:** 21/08/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Brian da Silva Guterres | [@brnsg] |

**Elemento de Competência:** Compreender os fundamentos de qualidade de software e sua aplicação no desenvolvimento de sistemas.

**Aplicação:** <https://local-eats-unisenac.vercel.app/>

---

## 2. Tarefa 1: Fundamentos da qualidade

### 2.1 Necessidades explícitas e implícitas

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
|---|---|---|---|
| Explícita | O sistema deve permitir criar conta e fazer login. | usuário | O usuário não consegue acessar sua conta e utilizar funcionalidades que dependem de autenticação. |
| Explícita | O sistema deve permitir que o usuário consiga selecionar o restaurante e pedir a comida. | usuário | O usuário não consegue fazer o pedido de comida. |
| Implícita | Todos os botões e abas clicáveis da interface (como "Cardápio" e "Avaliações") devem responder à interação do usuário e executar as ações esperadas (operabilidade). | usuário | O usuário clica em botões que não realizam ação alguma, gerando a percepção de que a página está travada ou quebrada. |
| Implícita | A barra de pesquisa deve filtrar os resultados exatamente pelos critérios indicados em seu texto orientador (como culinária e localização). | usuário | O usuário digita uma culinária no campo de busca e não encontra restaurantes, acreditando que a opção não existe na plataforma. |

### 2.2 Questão sobre os fundamentos da qualidade

**Um sistema que implementa todas as funcionalidades explicitamente solicitadas pode, ainda assim, apresentar baixa qualidade? Justifiquem utilizando pelo menos uma necessidade implícita identificada pela equipe.**

Sim. Um sistema pode possuir a funcionalidade de listar os pratos e as avaliações (necessidade explícita atendida), mas se os botões das abas na interface não funcionarem para alternar essa visão (necessidade implícita de operabilidade não atendida), a usabilidade será severamente comprometida. Essa falha em um detalhe implícito gera frustração e lentidão, caracterizando o software como um produto de baixa qualidade geral para o usuário final.

---

## 3. Tarefa 2: Exploração da aplicação

| Integrante | Funcionalidade | O que foi realizado | O que foi observado | Evidência |
|---|---|---|---|---|
| Brian da Silva Guterres | Controle de abas (Tabs) de Cardápio e Avaliações na página do restaurante | Clicar na aba "Avaliações" para exibir apenas as avaliações e ocultar o cardápio (e vice-versa ao clicar em "Cardápio"). | Os botões "Cardápio" e "Avaliações" são inoperantes e não alternam a exibição; ambos os conteúdos são renderizados juntos e de forma contínua um abaixo do outro na página, tornando os botões enganosos e sem funcionalidade real. | [ver evidência](evidencias/brian-abas-restaurante.mp4) |

---

## 4. Tarefa 3: Requisitos e características de qualidade

| Integrante | Requisito de Qualidade | Característica ou subcaracterística | Justificativa | Como avaliar |
|---|---|---|---|---|
| Brian da Silva Guterres | O sistema deve implementar a alternância efetiva entre as seções de Cardápio e Avaliações por meio do componente de abas, exibindo apenas o conteúdo correspondente à aba selecionada e mantendo um indicador visual claro do estado ativo. | Usabilidade / Operabilidade | A presença de controles inoperantes quebra o modelo mental do usuário (falsa affordance) e polui visualmente a tela ao exibir listas longas simultaneamente sem segregação. | Clicar na aba "Avaliações" e verificar se o cardápio fica oculto e apenas as avaliações permanecem visíveis, validando também o destaque visual na aba selecionada. |

---

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
Gemini

**Como foi utilizada:**  
Utilizada como apoio na estruturação do documento Markdown e para a formulação de ideias e refinamento da tabela de características de qualidade (ISO 25000).
Utilizada, também, para auxílio na formatação na linguagem de marcação "Markdown".

**Como as respostas foram verificadas:**  
Testei manualmente a aplicação LocalEats, validei as evidências coletadas e revisei os conceitos teóricos de qualidade de software do material de aula.
