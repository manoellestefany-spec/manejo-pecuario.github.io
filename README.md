# Sistema de Manejo Pecuário  

## Descrição de Minimundo  
Pequenas e médias propriedades rurais enfrentam dificuldades para controlar o histórico de saúde,vacinação  
rastreabilidade e ganho de peso do seu rebanho bovino. A ausência de um sistema centralizado resulta em perda de prazos de vacinação, dificuldades na identificação do histórico genético e falta de controle sobre os custos de manejo.
Este bancos de dados visa centralizar as informações do rebanho, permitindo ao produtor registrar cada animal, associá-lo a um lote específico na fazenda, acompanhar as vacinas aplicadas e registrar as pesagens ao longo do tempo.  
## Regras de Negócio  
1.Cada animal deve ser cadastrados individualmente com um brinco de identificação único.  
2.Um animal pertence a único lote por vez (ex:" Lote Engorda 1", "Lote Matrizes"), mas um lote pode ter vários animais.  
3.Um animal pode receber várias vacinas ao longo da vida, e uma mesma vacina pode ser aplicada em diversos animais.  
4.Cada aplicação de vacina deve registrar a data e a dose aplicada.  
5.Um animal passa por diversas pesagens para acompanhamento de desenvolvimento.  
6.Cada animal deve ter seu status registrado(em criação, vendido ou óbito). Em caso de venda, devem-se registrar a data, o peso final e o valor da transação; em decorrência de óbito, devem-se registrar a data e o motivo da perda.
## código do diagrama EER
```sql
CREATE DATABASE IF NOT EXISTS manejopecuario;
USE manejopecuario;

-- 1. Tabela PASTO
CREATE TABLE IF NOT EXISTS pasto (
    id_pasto INT AUTO_INCREMENT PRIMARY KEY,
    nome_pasto VARCHAR(100) NOT NULL,
    area_hectares DECIMAL(10,2),
    tipo_capim VARCHAR(50)
);

-- 2. Tabela LOTE (1:N com Pasto)
CREATE TABLE IF NOT EXISTS lote (
    id_lote INT AUTO_INCREMENT PRIMARY KEY,
    nome_lote VARCHAR(100) NOT NULL,
    capacidade_maxima INT,
    id_pasto INT NOT NULL,
    FOREIGN KEY (id_pasto) REFERENCES pasto(id_pasto)
);

-- 3. Tabela VENDA
CREATE TABLE IF NOT EXISTS venda (
    id_venda INT AUTO_INCREMENT PRIMARY KEY,
    data_venda DATE NOT NULL,
    comprador VARCHAR(150),
    valor_total DECIMAL(12,2)
);

-- 4. Tabela ANIMAL (1:N com Lote e Venda)
CREATE TABLE IF NOT EXISTS animal (
    id_animal INT AUTO_INCREMENT PRIMARY KEY,
    brinco_identificacao VARCHAR(50) NOT NULL UNIQUE,
    data_nascimento DATE,
    sexo CHAR(1),
    raca VARCHAR(50),
    status VARCHAR(20) DEFAULT 'Ativo',
    id_lote INT NOT NULL,
    id_venda INT NULL,
    FOREIGN KEY (id_lote) REFERENCES lote(id_lote),
    FOREIGN KEY (id_venda) REFERENCES venda(id_venda)
);

-- 5. Tabela PESAGEM (1:N com Animal)
CREATE TABLE IF NOT EXISTS pesagem (
    id_pesagem INT AUTO_INCREMENT PRIMARY KEY,
    data_pesagem DATE NOT NULL,
    peso_kg DECIMAL(6,2) NOT NULL,
    id_animal INT NOT NULL,
    FOREIGN KEY (id_animal) REFERENCES animal(id_animal)
);

-- 6. Tabela VACINA
CREATE TABLE IF NOT EXISTS vacina (
    id_vacina INT AUTO_INCREMENT PRIMARY KEY,
    nome_vacina VARCHAR(100) NOT NULL,
    fabricante VARCHAR(100),
    periodo_validade_dias INT
);

-- 7. Tabela APLICACAO_VACINA (N:N entre Animal e Vacina)
CREATE TABLE IF NOT EXISTS aplicacao_vacina (
    id_aplicacao INT AUTO_INCREMENT PRIMARY KEY,
    data_aplicacao DATE NOT NULL,
    dose_ml DECIMAL(5,2),
    id_animal INT NOT NULL,
    id_vacina INT NOT NULL,
    FOREIGN KEY (id_animal) REFERENCES animal(id_animal),
    FOREIGN KEY (id_vacina) REFERENCES vacina(id_vacina)
);

-- 8. Tabela OBITO (1:1 com Animal)
CREATE TABLE IF NOT EXISTS obito (
    id_obito INT AUTO_INCREMENT PRIMARY KEY,
    data_obito DATE NOT NULL,
    motivo VARCHAR(255),
    id_animal INT NOT NULL UNIQUE, -- UNIQUE garante a relação 1:1
    FOREIGN KEY (id_animal) REFERENCES animal(id_animal)
);

## imagem do diagrama
