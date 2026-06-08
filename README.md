# Projeto_Conceitual_dio
# 📦 Banco de Dados - E-commerce

Este projeto implementa um **modelo relacional de banco de dados** para um sistema de e-commerce.  
O objetivo é representar de forma estruturada as principais entidades e relacionamentos de um comércio eletrônico, incluindo clientes PF/PJ, produtos, fornecedores, pedidos, pagamentos e entregas.

---

## 🗂️ Estrutura do Banco de Dados

### Entidades principais
- **Cliente**
  - Suporta Pessoa Física (CPF) e Pessoa Jurídica (CNPJ), mas nunca ambos.
  - Campos: idCliente, Nome, TipoCliente (PF/PJ), CPF, CNPJ, E-mail, Telefone.

- **Endereço**
  - Um cliente pode ter múltiplos endereços (Casa, Trabalho, etc.).
  - Campos: idEndereco, idCliente (FK), TipoEndereco, Logradouro, Número, Bairro, Cidade, Estado, CEP.

- **Produto**
  - Campos: idProduto, Nome, Categoria, Descrição, Valor (DECIMAL).

- **Fornecedor**
  - Campos: idFornecedor, Razão Social, CNPJ, Contato.

- **Estoque**
  - Campos: idEstoque, idProduto (FK), QuantidadeDisponível, Local, DataAtualização.

- **Pedido**
  - Campos: idPedido, idCliente (FK), DataPedido, StatusPedido, ValorTotal, Frete, idEnderecoEntrega (FK).

- **ItemPedido**
  - Relaciona Pedido e Produto.
  - Campos: idItemPedido, idPedido (FK), idProduto (FK), Quantidade, PrecoUnitario.

- **Pagamento**
  - Um cliente pode ter várias formas de pagamento.
  - Campos: idPagamento, idCliente (FK), TipoPagamento (Cartão, Pix, Boleto), DadosPagamento, Validade.

- **Entrega**
  - Cada pedido possui status e código de rastreio.
  - Campos: idEntrega, idPedido (FK), StatusEntrega, CodigoRastreio, DataPrevista.

---

## 🔗 Relacionamentos
- Cliente 1:N Endereço  
- Cliente 1:N Pedido  
- Cliente 1:N Pagamento  
- Pedido 1:N ItemPedido  
- Pedido 1:1 Entrega  
- Produto N:N Pedido (via ItemPedido)  
- Produto N:N Fornecedor (via tabela intermediária)  
- Produto 1:N Estoque  

---

## 🚀 Como executar
1. Clone este repositório:
   ```bash
   git clone https://github.com/seuusuario/ecommerce-db.git
