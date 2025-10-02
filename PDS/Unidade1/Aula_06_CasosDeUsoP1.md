## Caso de Uso
### Motivação:
> Desenvolvimento Baseado em Planos (Tradicional):
- Segue um fluxo mais linear: a "Engenharia de Requisitos"(O que o sistema deve fazer e analisa) gera uma "Especificação de Requisitos" (detalhes e programação) formal, que só então é enviada para o "Projeto e Implementação" (desenho e codificação).

- Mudanças são tratadas formalmente por meio de uma "Solicitação de mudança", que reinicia o ciclo.

> Desenvolvimento Ágil:
- Funciona em um ciclo contínuo e interativo entre a "Engenharia de Requisitos" e o "Projeto e Implementação".

- Essa abordagem permite maior flexibilidade e adaptação a mudanças.

## Requisitos no Desenvolvimento Ágil
- No contexto ágil, os requisitos de software são organizados de uma forma específica para facilitar o trabalho em ciclos curtos (Sprints).

- **Épica** (Epic): É um grande bloco ou grupo de funcionalidades que possuem um objetivo de negócio em comum para atender a um requisito.

- História de Usuário (User Story): É uma descrição curta e simples de uma necessidade do usuário, escrita da perspectiva dele e sem detalhes técnicos.

- Formato Comum: "Como um <papel>, eu quero <objetivo> para que <benefício>".
- Exemplo: "Como um Administrador, quero convidar novos usuários para que meus colegas possam ver a informação".

## **Estrutura da Épica**:
``` md
RF001 – O sistema deve permitir que o usuário realize o pagamento online dos
produtos da cesta de compras, com transparência e confiabilidade.
> Épica 1: Realizar o pagamento online

- Como cliente, desejo visualizar as opções de pagamento disponíveis (cartão de crédito, débito, PIX), para escolher a conveniente.

- Como cliente, desejo inserir meus dados de pagamento de forma segura, para efetivar a transação sem riscos.

- Como cliente, desejo receber a confirmação do sucesso ou problema do pagamento,
para ter clareza sobre o resultado da transação
```

### Sobre a pirâmide:
A **quebra de trabalho em Agile** (Work Breakdown). Ela segue esta hierarquia:

1. **Product/Initiative** → é o objetivo maior ou produto final a ser desenvolvido.
2. **Epic** → grandes blocos de funcionalidades ou objetivos dentro do produto (macro).
3. **User Story** → descrições curtas do que o usuário precisa (em linguagem simples, centrada no usuário).
4. **Task** → atividades pequenas e técnicas necessárias para implementar cada *user story*.

Um **caso de uso** se aproxima de uma *user story*, mas é **mais detalhado**.

* **User Story** diz *“o que o usuário quer”* (ex.: *“Como estudante, quero repetir a lição anterior para revisar o conteúdo”*).
* **Caso de Uso** descreve **como isso acontece passo a passo**: atores, fluxos principal.
