# TabelaMercado

-- Criação da tabela "mercado"
CREATE TABLE mercado (
    id INT PRIMARY KEY,
    produto VARCHAR(100),
    preco_em_reais DECIMAL(10, 2),
    quantidade INT
);

-- Inserção de valores de produtos em reais
INSERT INTO mercado (id, produto, preco_em_reais, quantidade)
VALUES
    (1, 'Arroz', 5.99, 150),
    (2, 'Feijão', 3.49, 100),
    (3, 'Macarrão', 2.25, 200),
    (4, 'Leite', 3.79, 120),
    (5, 'Pão', 2.50, 250),
    (6, 'Carne', 25.50, 50),
    (7, 'Frango', 12.99, 70),
    (8, 'Ovos', 6.49, 180),
    (9, 'Açúcar', 2.99, 120),
    (10, 'Óleo de Cozinha', 7.25, 90);

-- Seleciona os 10 produtos mais comprados nos mercados
SELECT produto, SUM(quantidade) AS total_comprado
FROM mercado
GROUP BY produto
ORDER BY total_comprado DESC
LIMIT 10;

