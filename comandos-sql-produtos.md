# Comandos SQL - Referência

## Modelagem física

### Criar Banco de dados
```sql

CREATE DATABASE sistema CHARACTER SET utf8mb4;

```

<!-- ___________________________________________ -->

### Criar tabela generos
```sql

CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usuario VARCHAR(50) NOT NULL,
    senha VARCHAR(255) NOT NULL
);

CREATE TABLE fornecedores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100),
    telefone VARCHAR(20)
);

CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    fornecedor_id INT,
    nome VARCHAR(100) NOT NULL,
    descricao TEXT,
    preco DECIMAL(10, 2),
    FOREIGN KEY (fornecedor_id) REFERENCES fornecedores(id)
);

-- Cadastrar usuários
INSERT INTO usuarios (usuario, senha) VALUES ('Aninha', MD5('123'));
INSERT INTO usuarios (usuario, senha) VALUES ('Isinha', MD5('123'));


```

