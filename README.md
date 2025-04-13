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

