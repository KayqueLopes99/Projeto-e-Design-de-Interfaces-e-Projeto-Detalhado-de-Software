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

