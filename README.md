# Modelagem do Banco de Dados

Este documento descreve a estrutura do banco de dados conforme representado na imagem, incluindo as tabelas e relacionamentos.

## Tabelas

### Cliente

- **idCliente** (INT): Identificador único do cliente.
- **identificação** (VARCHAR(45)): Nome ou identificação do cliente.
- **endereço** (VARCHAR(45)): Endereço do cliente.
- **CPF** (VARCHAR(14)): CPF do cliente (opcional).
- **CNPJ** (VARCHAR(18)): CNPJ do cliente (opcional).
- **Restrição**: Apenas uma das colunas `CPF` ou `CNPJ` pode ser preenchida.

### FormaPagamento

- **idFormaPagamento** (INT): Identificador único da forma de pagamento.
- **tipoPagamento** (VARCHAR(45)): Tipo de pagamento (ex: cartão, boleto).
- **detalhes** (VARCHAR(45)): Detalhes adicionais sobre a forma de pagamento.
- **Cliente_idCliente** (INT): Chave estrangeira referenciando o cliente.

### Pedido

- **idPedido** (INT): Identificador único do pedido.
- **status_pedido** (VARCHAR(45)): Status atual do pedido.
- **observacao** (VARCHAR(45)): Observações adicionais sobre o pedido.
- **Cliente_idCliente** (INT): Chave estrangeira referenciando o cliente.
- **Frete** (FLOAT): Valor do frete.
- **StatusEntrega** (VARCHAR(45)): Status atual da entrega.
- **CodigoRastreio** (VARCHAR(45)): Código de rastreio da entrega.

## Relacionamentos

- **Cliente** pode ter múltiplas **Formas de Pagamento**.
- **Pedido** está associado a um **Cliente**.
- **Pedido** possui informações de **Status de Entrega** e **Código de Rastreio**.
