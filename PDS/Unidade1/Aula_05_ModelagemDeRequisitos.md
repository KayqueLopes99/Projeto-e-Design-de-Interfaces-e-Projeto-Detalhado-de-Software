## Modelagem de Requisitos
### **O que são Requisitos?**
* É uma condição ou capacidade que um usuário precisa para resolver um problema ou atingir um objetivo. Algo que o sistema é capaz de realizar para atingir os seus objetivos. 

* É uma descrição do que o sistema deve fazer para atender a uma necessidade de automação requerida pela solução.

* Desde as necessidades básicas do cliente, premissas e restrições obtidas na fase de levantamento do projeto até as condições de negócio explicitadas no contrato com o fornecedor da solução.

* Pode ser uma propriedade que o software deve ter para resolver um problema do mundo real.

* Descrições dos serviços fornecidos pelo sistema e das restrições sobre estes serviços.

> Em síntese, é o que o sistema deve fazer e como deve se comportar

(Ex: O sistema deve fornecer ...(Tal compotamento ou funcionalidade ou armazenar ou interagir)).

### **Técnicas de Elicitação (Obtenção) de Requisitos**
* **Elicitação**: Também chamada de "descoberta de requisitos", é o processo de obter as informações necessárias.

* **Envolvidos**: Deve envolver todos os interessados (*stakeholders*), como usuários finais, gerentes e especialistas no domínio do problema.


### **Tipos de Requisitos**
- Existem dois tipos principais de requisitos: Funcionais e Não-Funcionais.

#### **1. Requisitos Funcionais (RF)**
* **Definição**: Descrevem **o que o sistema deve fazer**.
    * Declaram os serviços que o sistema deve fornecer.
    * Definem como o sistema deve reagir a entradas específicas.
    * Especificam o que o sistema não deve fazer.
    * Comportamento ao providencias as funcionalidades de ``Cadastro e etc``.
     
* **Características**:
    * São detalhados e usados pela equipe de desenvolvimento.
    * Devem ser padronizados, completos e consistentes.
    * Fazem parte do contrato entre o cliente e o desenvolvedor.

* **Exemplos**:
    * `[RF001]` O sistema deve cadastrar o cliente.
    * `[RF002]` O sistema deve emitir um recibo para o cliente.

#### **2. Requisitos Não-Funcionais (RNF)**
* **Definição**: São **restrições e qualidades** sobre os serviços e funções oferecidos pelo sistema. Eles definem **como o sistema deve realizar** seus requisitos funcionais.
    - Geralmente se aplicam ao sistema como um todo.
    - Exemplos incluem restrições de tempo de resposta, padrões de desenvolvimento, etc.

* **Categorias**:
    * **Requisitos de Produto**: Qualidades do software em si (eficiência, confiabilidade, portabilidade, usabilidade).
    * **Requisitos Organizacionais**: Relacionados a políticas e procedimentos da empresa (padrões, entregas, implementação).
    * **Requisitos Externos**: Fatores externos ao sistema e à organização (leis, ética, interoperabilidade).

* **Exemplos**:
    * **Produto**: "A interface do usuário deve ser implementada como simples HTML.
    * **Organizacional**: "Todos os documentos devem seguir o padrão de relatórios XYZ-00".
    * **Externo**: "Informações pessoais dos usuários não podem ser vistas pelos operadores do sistema (LGPD)".

### **Regras de Negócio** --> Requisitos:
* **Definição**: São políticas ou condições que devem ser cumpridas, ditando como o negócio deve operar. Podem ser leis ou o estilo de negócio escolhido pela empresa.
  
- São tipos de requisitos de como os negócios, incluindo suas ferramentas de negócios, devem operar.

* **Importância**: Podem ser reutilizadas em vários projetos. Separar as regras de negócio dos requisitos é uma boa prática de engenharia de software.

* **Exemplos**:
    * "O preço líquido de um Produto é computado por preço do produto (1+porcentagem de imposto/100)".
    * "Para ser considerado dependente, a pessoa não pode ter renda ou a renda deve ser abaixo de um salário mínimo".

### **Forma de Representação dos Requisitos**
| Notação (Código) | Requisito (Título) | Requisito (Definição) |
| :--- | :--- | :--- |
| RFx ou RNFx| conteudo | conteudo |

* **Linguagem Natural Estruturada**: Usa formulários ou templates-padrão para expressar os requisitos, mantendo a facilidade de leitura mas garantindo uniformidade
> Uniformidade e Tabelas.


### **Diretrizes para Elaboração de Requisitos**

* Use um formato padrão e linguagem consistente **("deve" para obrigatório, "deveria" para desejável)**.
* Evite jargões de computação, ambiguidades e termos vagos.
* Use sentenças diretas, objetivas e curtas.
* Defina requisitos que possam ser verificados.
* Evite sentenças muito longas.
* Evite o uso de conjunções como ou, e, com, também. 

---