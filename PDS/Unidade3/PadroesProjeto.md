### 1. Decorator (Estrutural)
**Definição:**
O Decorator permite adicionar comportamentos a um objeto dinamicamente (em tempo de execução) sem alterar o código da classe original e sem usar herança excessiva. Ele funciona como uma "casca" ou "envoltório" (wrapper).

- "Boneca russa": você pode empilhar vários decoradores em um objeto.

##### Como implementar
> 1. Analise o Problema (O Cenário)
- Verifique se o seu objeto precisa receber funcionalidades adicionais em "camadas" (como uma cebola).
- Identifique o Componente Principal (ex: um Café simples) e as Camadas Opcionais (ex: Leite, Canela, Chantilly).

> 2. Crie a Interface Comum (Component)
- Defina uma interface (ou classe abstrata) que contenha os métodos comuns tanto para o objeto principal quanto para os decoradores. Para que o cliente trate o objeto simples e o objeto "decorado" exatamente da mesma maneira.

> 3. Implemente o Componente Concreto
- Crie a classe que representa o objeto base (o núcleo). Implemente a interface criada no passo 2. Defina o comportamento padrão, sem nenhuma decoração.

> 4. Crie a Classe Decoradora Base (BaseDecorator)
- Crie uma classe que também implementa a interface do passo 2. Esta classe deve ter um campo (propriedade) para armazenar uma referência a um objeto do tipo da interface (Component). No método principal, ela não faz nada "novo"; ela apenas delega (repassa) a chamada para o objeto armazenado nesse campo.

> 5. Crie os Decoradores Concretos (ConcreteDecorators)
Crie classes que estendem o BaseDecorator criado no passo 4. Implemente a lógica extra (a "decoração"). O método deve executar sua nova funcionalidade (antes ou depois) e chamar o método do pai (super.metodo()), que por sua vez chama o próximo objeto da pilha.

> 6. Composição (O Código Cliente)
- No código principal (Main/Client), monte as camadas conforme a necessidade.
- Exemplo de montagem:

Cria o objeto base.
Passa o objeto base para dentro do primeiro decorador.
Passa o resultado para dentro do segundo decorador, e assim por diante.

**Quando usar:**
* Quando você precisa adicionar funcionalidades a objetos individuais, não à classe inteira.
* Para evitar uma explosão de subclasses (ex: `CafeComLeite`, `CafeComChocolate`, `CafeComLeiteEChocolate`).

---

### 2. State (Comportamental)
**Definição:**
- O State é um padrão de projeto comportamental que permite que um objeto altere seu comportamento quando seu estado interno muda. Parece como se o objeto mudasse de classe.



##### Como implementar

1. **Defina a Interface do Estado** - Declare os métodos que representam as ações possíveis (ex: `pagar()`, `enviar()`, `cancelar()`).

2. **Crie Classes Concretas para Cada Estado** - Para cada estado possível, implemente a interface. Cada classe define o comportamento específico daquele estado.

3. **Implemente a Classe Contexto** - Adicione um campo para armazenar o estado atual e um setter para alterá-lo. Delegue as chamadas de métodos para o objeto de estado.

4. **Implemente as Transições** - Dentro das classes de estado (ou no contexto), defina para qual estado o objeto deve transicionar após cada ação.

5. **Use no Código Cliente** - Crie o contexto com um estado inicial e chame seus métodos normalmente; as transições ocorrem automaticamente.


**Como funciona:**
* Em vez de ter um código cheio de condicionais (`if status == 'PAGO' then...`), você cria uma classe para cada estado possível.
* O objeto principal (Contexto) delega a execução do comportamento para o objeto de Estado atual.

**Exemplo Prático (Status de Pedido):**
* **Estado `Aberto`:** Se o usuário clicar em "Pagar", transiciona para o estado `Pago`. Se clicar em "Cancelar", vai para `Cancelado`.
* **Estado `Pago`:** O método "Pagar" não faz nada (ou lança erro). O método "Enviar" transiciona para `Enviado`.
* **Estado `Enviado`:** Não permite cancelar nem pagar.

**Quando usar:**
* Quando o comportamento de um objeto depende do seu estado e muda em tempo de execução.
* Para eliminar condicionais complexas e máquinas de estado gigantescas.

---

### 3. Observer (Comportamental)
**Definição:**
- O Observer é um padrão de projeto comportamental que permite que você defina um mecanismo de assinatura para notificar múltiplos objetos sobre quaisquer eventos que aconteçam com o objeto que eles estão observando.

**Como funciona:**
* O **Sujeito** (Subject) mantém uma lista de inscritos.
* O **Observador** (Observer) se inscreve no Sujeito.
* Quando algo acontece no Sujeito, ele percorre a lista e chama um método de atualização em cada Observador.

**Exemplo Prático:**
* **Newsletter:** O blog é o Sujeito; os leitores são os Observadores. Quando sai um post novo, todos recebem e-mail.
* **Interface Gráfica (Listeners):** O botão é o Sujeito. O código que reage ao clique é o Observador.
* **Youtube:** O canal é o sujeito, os inscritos são os observadores.

**Quando usar:**
* Quando a mudança em um objeto exige mudanças em outros, e você não sabe quantos objetos precisam mudar.
* Para criar sistemas desacoplados (o Sujeito não precisa saber quem são os Observadores nem o que eles fazem).

---

### 4. Adapter (Estrutural)

**Definição:**
Permite que classes com interfaces incompatíveis trabalhem juntas. Ele atua como um tradutor entre dois objetos que, de outra forma, não conseguiriam se comunicar.



**Como funciona:**
* O **Adapter** implementa a interface que o cliente espera.
* Dentro dele, ele chama os métodos do objeto incompatível (Adaptee), convertendo os dados se necessário.

**Exemplo Prático:**
* **Tomadas:** Um adaptador de tomada (padrão antigo de 2 pinos para o novo de 3 pinos).
* **Sistemas Legados:** Seu sistema espera dados em formato `JSON`, mas precisa consumir uma API antiga de um banco que retorna `XML`. Você cria um Adapter que recebe XML, converte e entrega JSON para seu sistema.

**Quando usar:**
* Quando você quer usar uma classe existente, mas sua interface não corresponde à que você precisa.
* Para integrar bibliotecas de terceiros ou sistemas legados sem alterar o código original deles.

---

### 5. Facade (Estrutural)

**Definição:**
Fornece uma interface simplificada (uma "fachada") para um subsistema complexo contendo muitas classes e partes móveis.

**Como funciona:**
* A classe **Facade** conhece quais classes do subsistema são responsáveis por uma solicitação e delega as chamadas para os objetos apropriados.
* O cliente interage apenas com a Facade, sem precisar conhecer a complexidade interna.

**Exemplo Prático:**
* **Ligar Computador:** Ao apertar o botão "Ligar" (Facade), o sistema internamente: verifica a energia -> inicia a CPU -> carrega a memória -> monta o disco -> inicia o SO. O usuário só apertou um botão.
* **E-commerce:** Um método `finalizarCompra()` na Facade pode, internamente, chamar o `ServicoDeEstoque`, `ServicoDePagamento`, `ServicoDeNotaFiscal` e `ServicoDeEnvio`.

**Quando usar:**
* Para oferecer uma interface simples para uma biblioteca complexa.
* Para desacoplar seu código de subsistemas complexos (se o subsistema mudar, você só altera a Facade, não o código todo).

---
