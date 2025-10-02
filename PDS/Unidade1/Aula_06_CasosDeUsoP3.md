# Estrutura da Narrativa de um Caso de Uso
A descrição de um Caso de Uso detalha o passo a passo de uma funcionalidade.  
Segue a estrutura usada normalmente:

* **Objetivo (ou Brief Description)**: Uma ou duas frases que resumem a finalidade do caso de uso. O que ele permite que o ator faça?
* **Ator (Actor)**: 

Indica quem (ou o quê) irá interagir com o sistema para executar esta funcionalidade.
* **Pré-Condições (Preconditions)**: 

O que precisa ser verdade **antes** que o caso de uso possa começar. Ex.: o usuário precisa estar logado, o cadastro precisa existir, etc.
* **Condição de Entrada / pós condições**: 

A ação específica que o ator realiza para iniciar o caso de uso (ex: clicar em um botão).
* **Fluxo Principal (Basic Flow of Events)**: 

Este é o "caminho feliz". Sequência numerada que descreve a interação quando tudo ocorre como esperado, sem erros ou desvios.
* **Fluxos Alternativos (Alternative Flows)**:

Caminhos de exceção ou alternativos. São as variações que podem ocorrer no Fluxo Principal (erros, cancelamentos, condições diferentes).
    * **Sintaxe Importante**: Usam-se marcadores como `[A1]`, `[A2]` no Fluxo Principal. Eles são "gatilhos". Se em um determinado passo algo diferente acontecer, a execução "pula" para o fluxo alternativo correspondente.
* **Pós-Condições (Post-conditions)**: 

O que deve ser verdade **depois** que o caso de uso termina com sucesso. Qual é o estado final do sistema?

---

### Exemplo: Caso de Uso "Reservar Livro"

**Objetivo**: Este caso de uso possibilita a um usuário da biblioteca fazer a reserva de um livro. Esta reserva é efetuada diretamente pelo Usuário usando a Internet.

**Ator**: Usuário  

**Pré-Condições**: O Usuário é cadastrado na Biblioteca. O Usuário já foi autenticado pelo Sistema.  

**Condição de Entrada**: O ator usuário decide reservar um livro e escolhe a opção correspondente.  

---

## Fluxo Principal
1. O sistema exibe formulário com o campo livro e as opções buscar e cancelar.  
2. Usuário fornece a identificação do livro desejado e escolhe buscar **`[A1]`** **`[A2]`**.  
3. O sistema localiza o livro desejado.  
4. O sistema verifica a disponibilidade de exemplar do livro desejado.  
5. O sistema exibe mensagem de livro disponível **`[A3]`**.  
6. O sistema verifica o número de reservas em aberto para o usuário (RN01).  
7. O sistema efetua a reserva e informa ao usuário o prazo máximo para a retirada do livro (RN02) **`[A4]`**.  
8. O caso de uso se encerra.  

---

## Fluxos Alternativos

**A1**: O usuário escolhe cancelar.  
1. Volta para página inicial.  
2. Caso de uso é encerrado.  

**A2**: O livro solicitado não foi encontrado.  
1. Exibe mensagem de livro não encontrado.  
2. Volta para o passo 1 do fluxo principal.  

**A3**: Não existe nenhum exemplar disponível.  
1. Exibe mensagem de nenhum exemplar disponível.  
2. Sistema verifica a data de devolução prevista para o livro solicitado.  
3. Informa data prevista para que haja um exemplar disponível.  
4. O sistema pergunta ao usuário se ele deseja efetuar a reserva de exemplar não disponível.  
5. Se o usuário responder afirmativamente, o sistema o informa que será contatado quando o livro estiver disponível e retorna ao passo 6 do Fluxo Principal. Caso contrário, o caso de uso se encerra.  

**A4**: O usuário excedeu o número máximo de reservas em aberto.  
1. O sistema reporta uma mensagem adequada para o Usuário.  
2. O Caso de Uso se encerra.  

---

# Prós e Contras

**Casos de Uso (Prós)**: São mais formais e claros, bons para documentação técnica e para ter uma análise inicial robusta.  

**Casos de Uso (Contras)**: São mais rígidos e difíceis de mudar, menos amigáveis para o cliente final e o processo é mais demorado.  
