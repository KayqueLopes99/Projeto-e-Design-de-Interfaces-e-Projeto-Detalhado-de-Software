## Detalhamento dos Requisitos
![](image/image16.png)

---
> User Stories (Histórias de Usuário):
- Nível de Detalhe: Baixo (Low). São curtas e simples.
- Nível de Especificação: Baixo (Low). Não entram em detalhes técnicos.
- Uso: Ideal para metodologias ágeis, focando na necessidade do usuário.

> Traditional Requirement (Requisito Tradicional):
- Fica em um nível intermediário entre as Histórias de Usuário e os Casos de Uso.

> Use Cases (Casos de Uso):
- Nível de Detalhe: Alto (High). Descrevem a interação passo a passo.
- Nível de Especificação: Alto (High). São mais formais e detalhados.
- Uso: Ideal para o desenvolvimento baseado em planos (tradicional), onde é preciso um documento completo antes de começar a programar.

### O que é um Caso de Uso?
- Definição: Casos de uso são modelos que descrevem como os usuários interagem com um sistema para realizar tarefas específicas.

- Objetivo: Descrevem, de forma clara, como o sistema deve se comportar a partir da interação com os usuários.

- Visão: Oferecem uma visão simplificada de uma interação, mostrando a funcionalidade do sistema do ponto de vista do usuário.

### Diagrama de Caso de Uso

### 1. **Atores**
* Representam **quem interage** com o sistema (pessoas, outros sistemas, dispositivos).
* Ex.: *Estudante, Professor, Administrador*.

### 2. **Casos de uso**
* São as **funcionalidades ou serviços** que o sistema oferece aos atores.
* Ex.: *Executar lição anterior, Gerenciar dicas, Registrar presença*.


### 3. **Relacionamentos entre estes**
* Mostram como atores e casos de uso se conectam.
* Ex.: O ator *Estudante* está ligado ao caso de uso *Executar lição anterior*.

### 4. **Associações**
* Linhas que ligam **atores** e **casos de uso**.
* Indicam que o ator participa daquela funcionalidade.

### 5. **Generalização entre atores**
* Mostra que um ator **herda o comportamento** de outro.
* Ex.: *Usuário* pode ser ator genérico, e *Estudante* e *Professor* herdam dele.

### 6. **Generalização, «extends» e «includes» entre os casos de uso**
* **Generalização** → um caso de uso genérico com versões especializadas.
* **«include»** → quando um caso de uso sempre **inclui outro** como parte da sua execução.
  * Ex.: *Executar lição anterior* **inclui** *Autenticar-se*.
* **«extend»** → quando um caso de uso pode ser **estendido opcionalmente** por outro.
  * Ex.: *Executar lição anterior* pode ser estendido por *Revisar dicas extras*.

### 7. **Limites do sistema**
* Representados por um **retângulo** que engloba os casos de uso.
* Dentro do retângulo → estão os casos de uso (funcionalidades).
* Fora do retângulo → ficam os atores que interagem com o sistema.

* Em resumo:
Um **diagrama de casos de uso** mostra:
* **Quem usa o sistema (atores)**,
* **O que o sistema faz (casos de uso)**,
* **Como se relacionam (associações, includes, extends, generalização)**,
* **E qual é o limite do sistema** (retângulo que engloba os casos de uso).

---
> Atores (Humano ou outro sistema): Simbolo de pessoa.

> Caso de uso (função): Simbolo de  um circulo achatado.

> Relacionamento de associação (entre ator e caso de uso): Simbolo de uma seta do ator para o caso.

> Relacionamento de generalização (entre atores): Simbolo de uma seta com ponta branca do ator B para o ator B. Isso idica que os casos de uso de B serão tbm os de A.

> Entre os casos de uso <<include>>: quando um caso de uso sempre **inclui outro** como parte da sua execução. Simbolo de um seta pontilhada do caso A para o B.

> Entre os casos de uso <<estends>>: quando um caso de uso pode ser **estendido opcionalmente** por outro

> Retângo em torno dos casps de uso, pois limita o sistema, deixando os atores fora do retângulo sempre.

---
![](image/image17.png)

---

