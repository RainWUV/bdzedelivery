# bdzedelivery
O banco de dados do Zé Delivery registra dados de usuários, vendedores, produtos, pedidos, entregas e vendas, com relacionamentos para garantir a integridade e suportar operações eficientes e relatórios.
# Banco de Dados do Aplicativo Zé Delivery

Este é o README.md para documentar a estrutura do banco de dados do aplicativo Zé Delivery. O banco de dados é projetado para atender às necessidades do aplicativo, incluindo o registro de usuários, pedidos, produtos, vendas, relatórios de vendas, formas de pagamento, estoque, entregas e informações de lojas físicas.

## Tabelas

O banco de dados é composto pelas seguintes tabelas:

1. **Usuários/Clientes:**
   - cod_cliente (Chave Primária)
   - Login
   - Senha (criptografada)
   - Nome
   - CPF
   - Email
   - Endereço
   - Telefone

2. **Vendedores:**
   - cod_vendedor (Chave Primária)
   - Código_loja fisica (Chave Estrangeira)
   - Código_cliente (Chave Estrangeira)
   - Nome do Vendedor
   - Telefone do Vendedor
   - Campo Admin

3. **Lojas Físicas:**
   - cod_Loja Física (Chave Primária)
   - Nome da Loja
   - Endereço da Loja
   - Telefone da Loja

4. **Fornecedores de Bebidas:**
   - cod_Fornecedor (Chave Primária)
   - Nome do Fornecedor

5. **Produtos:**
   - cod_Produto (Chave Primária)
   - Nome do Produto
   - Código_Fornecedor (Chave Estrangeira)
   - Quantidade em Estoque

6. **Estoque:**
   - cod_Estoque (Chave Primária)
   - cod_Produto (Chave Estrangeira)
   - Quantidade em Estoque

7. **Pedidos:**
   - cod_Pedido (Chave Primária)
   - cod_Usuário (Chave Estrangeira)
   - cod_Vendedor (Chave Estrangeira)
   - cod_Entrega (Chave Estrangeira)
   - cod_Forma de Pagamento (Chave Estrangeira)
   - Data e Hora do Pedido
   - Status do Pedido (PEDIDO REALIZADO, EM ANDAMENTO, A CAMINHO, ENTREGUE)
   - Valor Total do Pedido
   - Tempo de Espera Atual

9. **Entregas:**
   - cod_Entrega (Chave Primária)
   - cod_Pedido (Chave Estrangeira)
   - Status da Entrega (pendente, entregue)
   - Endereço de Entrega

10. **Formas de Pagamento:**
    - cod_Forma de Pagamento (Chave Primária)
    - Nome da Forma de Pagamento
    - Descrição da Forma de Pagamento

11. **Vendas:**
    - cod_Venda (Chave Primária)
    - cod_Loja Física (Chave Estrangeira)
    - cod_Pedido (Chave Estrangeira)
    - cod_Forma de Pagamento (Chave Estrangeira)
    - Data da Venda
    - Valor Total da Venda

12. **Relatórios Mensais de Vendas:**
    - cod_Relatório (Chave Primária)
    - cod_Loja Física (Chave Estrangeira)
    - Valor Total de Vendas
    - Data de Início do Relatório
    - Data de Fim do Relatório

## Relacionamentos

- A tabela de Usuários/Clientes está relacionada à tabela de Pedidos pelo campo "ID do Usuário".
- A tabela de Vendedores está relacionada à tabela de Lojas Físicas pelo campo "Código da Loja Física".
- A tabela de Vendedores também está relacionada à tabela de Usuários/Clientes pelo campo "Código do Usuário".
- A tabela de Produtos está relacionada à tabela de Estoque pelo campo "ID do Produto".
- A tabela de Pedidos está relacionada à tabela de Itens do Pedido pelo campo "ID do Pedido".
- A tabela de Pedidos também está relacionada à tabela de Entregas pelo campo "ID da Entrega".
- A tabela de Pedidos está relacionada à tabela de Formas de Pagamento pelo campo "ID da Forma de Pagamento".
- A tabela de Produtos está relacionada à tabela de Itens do Pedido pelo campo "ID do Produto".
- A tabela de Lojas Físicas está relacionada à tabela de Vendas pelo campo "ID da Loja Física".
- A tabela de Lojas Físicas também pode estar relacionada à tabela de Relatórios Mensais de Vendas pelo campo "ID da Loja Física".
- A tabela de Pedidos está relacionada à tabela de Vendas pelo campo "ID do Pedido".
- A tabela de Vendas está relacionada à tabela de Formas de Pagamento pelo campo "ID da Forma de Pagamento".

## Uso

Esta estrutura de banco de dados foi projetada para atender aos requisitos do aplicativo Zé Delivery. Certifique-se de configurar os relacionamentos de acordo com as chaves primárias e estrangeiras correspondentes em seu banco de dados para garantir a integridade dos dados e atender aos requisitos do sistema.

Para informações adicionais sobre como usar ou modificar o banco de dados, consulte a documentação do sistema ou entre em contato com o desenvolvedor responsável.

