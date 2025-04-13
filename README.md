# Desafio-Bootcamp-DIO

CREATE TABLE Cliente (
    ClienteID INT PRIMARY KEY,
    Tipo VARCHAR(2) CHECK (Tipo IN ('PJ', 'PF')),
    Nome VARCHAR(100),
    ...
);

INSERT INTO Cliente (ClienteID, Tipo, Nome) VALUES 
(1, 'PJ', 'Empresa X'),
(2, 'PF', 'João Silva');

SELECT Nome FROM Cliente WHERE Tipo = 'PF';

SELECT * FROM Pedido WHERE Data > '2025-01-01';

SELECT ProdutoID, Preco * Quantidade AS ValorTotal FROM ItemPedido;

SELECT Nome FROM Fornecedor ORDER BY Nome ASC;

SELECT ClienteID, COUNT(*) AS TotalPedidos
FROM Pedido
GROUP BY ClienteID
HAVING COUNT(*) > 5;

SELECT c.Nome, p.ProdutoNome 
FROM Cliente c
INNER JOIN Pedido pd ON c.ClienteID = pd.ClienteID
INNER JOIN Produto p ON pd.ProdutoID = p.ProdutoID;




Descrição do Projeto
Este repositório apresenta a implementação de um esquema de banco de dados para um cenário de e-commerce, seguindo as melhores práticas de modelagem lógica e implementando consultas SQL complexas para análise de dados.
Objetivo
O objetivo deste projeto é:
- Criar um banco de dados que suporte a gestão de um e-commerce com os seguintes refinamentos:- Clientes podem ser Pessoa Física (PF) ou Pessoa Jurídica (PJ), mas não ambos.
- Registro de múltiplas formas de pagamento para cada pedido.
- Controle de status e rastreamento de entregas.


Estrutura do Banco de Dados
O banco de dados foi modelado com base no seguinte modelo lógico:
- Entidades: Cliente, Pedido, Produto, Fornecedor, Estoque, Entrega, Forma de Pagamento.
- Relacionamentos principais:- Cada cliente pode realizar vários pedidos.
- Um pedido pode conter múltiplas formas de pagamento.
- Produtos são fornecidos por fornecedores e gerenciados em estoques.
- Pedidos estão associados a entregas, que possuem status e códigos de rastreamento.


Scripts e Implementação
Criação de Tabelas
Scripts para criar tabelas com definição de:
- Chaves primárias e estrangeiras.
- Restrições como CHECK para validar tipo de cliente (PJ ou PF).

Inserção de Dados
Scripts para popular as tabelas com dados fictícios para realização de testes.
Consultas SQL
- Recuperações simples com SELECT.
- Filtros com WHERE.
- Atributos derivados (ex.: cálculo de valores totais).
- Ordenação com ORDER BY.
- Filtros em grupos com HAVING.
- Junções entre tabelas para análise mais aprofundada.



