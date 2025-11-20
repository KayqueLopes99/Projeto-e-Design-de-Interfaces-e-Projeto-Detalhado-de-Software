classDiagram
    direction TB %% Top-to-Bottom, como na imagem %%

    class Client {
        + idCliente: String
        + nome: String
        + email: String
        + endereco: String
        + comprarItem(produtoId: String, quantidade: int): boolean
    }

    class VendaOnlineFacade {
        %% O Facade conhece todos os subsistemas, como na imagem %%
        - estoqueSubsystem: EstoqueSubsystem
        - pagamentoSubsystem: PagamentoSubsystem
        - logisticaSubsystem: LogisticaSubsystem
        
        + realizarPedido(produtoId: String, quantidade: int, clienteId: String): boolean
        + consultarEstoque(produtoId: String): int
        + adicionarProdutoEstoque(produtoId: String, nome: String, quantidade: int, preco: double): boolean
    }

    class EstoqueSubsystem {
        - itensEstoque: Map~String, ProdutoEstoque~
        
        + adicionarProduto(produtoId: String, nome: String, quantidade: int, preco: double): boolean
        + removerProduto(produtoId: String, quantidade: int): boolean
        + consultarQuantidade(produtoId: String): int
        + verificarDisponibilidade(produtoId: String, quantidade: int): boolean
        + getProduto(produtoId: String): ProdutoEstoque
    }

    class ProdutoEstoque {
        + produtoId: String
        + nome: String
        + quantidade: int
        + preco: double
    }

    class PagamentoSubsystem {
        - transacoes: Map~String, Transacao~
        %% Na estrutura da imagem, o Pagamento precisa conhecer o Estoque %%
        ~ estoque: EstoqueSubsystem
        
        + processarPagamento(clienteId: String, produtoId: String, quantidade: int, metodoPagamento: String): boolean
        + estornarPagamento(transacaoId: String): boolean
    }

    class LogisticaSubsystem {
        - pedidos: Map~String, PedidoLogistica~
        %% Na estrutura da imagem, a Logística precisa conhecer outros subsistemas %%
        ~ pagamento: PagamentoSubsystem
        ~ cliente: Client
        
        + agendarEntrega(produtoId: String, clienteId: String, transacaoId: String): boolean
        + rastrearEntrega(pedidoId: String): String
    }

    %% --- Relacionamentos --- %%
    
    %% O Client usa apenas o Facade %%
    Client --> VendaOnlineFacade : usa
    
    %% O Facade gerencia todos os subsistemas (como o HomeTheaterFacade) %%
    VendaOnlineFacade o-- EstoqueSubsystem
    VendaOnlineFacade o-- PagamentoSubsystem
    VendaOnlineFacade o-- LogisticaSubsystem
    
    %% --- Links Laterais (A ESTRUTURA DA IMAGEM) --- %%
    %% Assim como o Amplificador conhece o DVD, o Pagamento conhece o Estoque %%
    PagamentoSubsystem --> EstoqueSubsystem : consulta preco
    
    %% A Logística consulta o Pagamento e o Cliente %%
    LogisticaSubsystem --> PagamentoSubsystem : verifica status
    
    %% Relacionamento interno do Estoque %%
    EstoqueSubsystem *-- ProdutoEstoque