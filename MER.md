# Modelo de Entidade e Relacionamento (MER) - Manejo Pecuário

## 1. Entidades

* **Animal:** Representa cada bovino individualmente na propriedade.
* **Lote:** Representa a área ou agrupamento de manejo onde o animal está alocado.
* **Vacina:** Representa o tipo de vacina/medicamento disponível no catálogo da fazenda.
* **Pesagem:** Registra a evolução do peso do animal ao longo do tempo.
* **Aplicacao_Vacina:** Registra os eventos de imunização aplicados a cada animal.  

## 2. Relacionamentos e Cardinalidades

* **[Lote] (1,1) <abriga> (0,N) [Animal]**
  * *Explicação:* Um Lote pode abrigar vários Animais (N), mas cada Animal deve estar em apenas um Lote específico por vez (1).

* **[Animal] (1,1) <registra> (0,N) [Pesagem]**
  * *Explicação:* Um Animal pode ter várias Pesagens registradas ao longo do tempo (N), mas cada Pesagem pertence obrigatoriamente a apenas um Animal específico (1).

* **[Animal] (1,1) <recebe> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Um Animal pode ter vários registros de aplicação de vacinas (N), mas cada aplicação pertence a um único Animal (1).

* **[Vacina] (1,1) <usada_em> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Uma Vacina pode ser utilizada em diversas aplicações (N), mas cada registro de aplicação refere-se a apenas um tipo de Vacina (1).

## 3. Sugestão de Atributos

* **Animal**
  * `id_animal` (PK - Chave Primária)
  * `brinco_identificacao` (Atributo Único)
  * `data_nascimento`
  * `sexo`
  * `raca`
  * `id_lote` (FK - Chave Estrangeira)

* **Lote**
  * `id_lote` (PK - Chave Primária)
  * `nome_lote`
  * `capacidade_maxima`
  * `pasto_localizacao`

* **Vacina**
  * `id_vacina` (PK - Chave Primária)
  * `nome_vacina`
  * `fabricante`
  * `periodo_validade_dias`

* **Pesagem**
  * `id_pesagem` (PK - Chave Primária)
  * `data_pesagem`
  * `peso_kg`
  * `id_animal` (FK - Chave Estrangeira)

* **Aplicacao_Vacina**
  * `id_aplicacao` (PK - Chave Primária)
  * `data_aplicacao`
  * `dose_ml`
  * `id_animal` (FK - Chave Estrangeira)
  * `id_vacina` (FK - Chave Estrangeira)

---

## 4. Diagrama Entidade e Relacionamento (DER)

# Modelo de Entidade e Relacionamento (MER) - Manejo Pecuário

## 1. Entidades

* **Animal:** Representa cada bovino individualmente na propriedade.
* **Lote:** Representa a área ou agrupamento de manejo onde o animal está alocado.
* **Vacina:** Representa o tipo de vacina/medicamento disponível no catálogo da fazenda.
* **Pesagem:** Registra a evolução do peso do animal ao longo do tempo.
* **Aplicacao_Vacina:** Registra os eventos de imunização aplicados a cada animal.  

## 2. Relacionamentos e Cardinalidades

* **[Lote] (1,1) <abriga> (0,N) [Animal]**
  * *Explicação:* Um Lote pode abrigar vários Animais (N), mas cada Animal deve estar em apenas um Lote específico por vez (1).

* **[Animal] (1,1) <registra> (0,N) [Pesagem]**
  * *Explicação:* Um Animal pode ter várias Pesagens registradas ao longo do tempo (N), mas cada Pesagem pertence obrigatoriamente a apenas um Animal específico (1).

* **[Animal] (1,1) <recebe> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Um Animal pode ter vários registros de aplicação de vacinas (N), mas cada aplicação pertence a um único Animal (1).

* **[Vacina] (1,1) <usada_em> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Uma Vacina pode ser utilizada em diversas aplicações (N), mas cada registro de aplicação refere-se a apenas um tipo de Vacina (1).

## 3. Sugestão de Atributos

* **Animal**
  * `id_animal` (PK - Chave Primária)
  * `brinco_identificacao` (Atributo Único)
  * `data_nascimento`
  * `sexo`
  * `raca`
  * `id_lote` (FK - Chave Estrangeira)

* **Lote**
  * `id_lote` (PK - Chave Primária)
  * `nome_lote`
  * `capacidade_maxima`
  * `pasto_localizacao`

* **Vacina**
  * `id_vacina` (PK - Chave Primária)
  * `nome_vacina`
  * `fabricante`
  * `periodo_validade_dias`

* **Pesagem**
  * `id_pesagem` (PK - Chave Primária)
  * `data_pesagem`
  * `peso_kg`
  * `id_animal` (FK - Chave Estrangeira)

* **Aplicacao_Vacina**
  * `id_aplicacao` (PK - Chave Primária)
  * `data_aplicacao`
  * `dose_ml`
  * `id_animal` (FK - Chave Estrangeira)
  * `id_vacina` (FK - Chave Estrangeira)

---

## 4. Diagrama Entidade e Relacionamento (DER)
# Modelo de Entidade e Relacionamento (MER) - Manejo Pecuário

## 1. Entidades

* **Animal:** Representa cada bovino individualmente na propriedade.
* **Lote:** Representa a área ou agrupamento de manejo onde o animal está alocado.
* **Vacina:** Representa o tipo de vacina/medicamento disponível no catálogo da fazenda.
* **Pesagem:** Registra a evolução do peso do animal ao longo do tempo.
* **Aplicacao_Vacina:** Registra os eventos de imunização aplicados a cada animal.  

## 2. Relacionamentos e Cardinalidades

* **[Lote] (1,1) <abriga> (0,N) [Animal]**
  * *Explicação:* Um Lote pode abrigar vários Animais (N), mas cada Animal deve estar em apenas um Lote específico por vez (1).

* **[Animal] (1,1) <registra> (0,N) [Pesagem]**
  * *Explicação:* Um Animal pode ter várias Pesagens registradas ao longo do tempo (N), mas cada Pesagem pertence obrigatoriamente a apenas um Animal específico (1).

* **[Animal] (1,1) <recebe> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Um Animal pode ter vários registros de aplicação de vacinas (N), mas cada aplicação pertence a um único Animal (1).

* **[Vacina] (1,1) <usada_em> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Uma Vacina pode ser utilizada em diversas aplicações (N), mas cada registro de aplicação refere-se a apenas um tipo de Vacina (1).

## 3. Sugestão de Atributos

* **Animal**
  * `id_animal` (PK - Chave Primária)
  * `brinco_identificacao` (Atributo Único)
  * `data_nascimento`
  * `sexo`
  * `raca`
  * `id_lote` (FK - Chave Estrangeira)

* **Lote**
  * `id_lote` (PK - Chave Primária)
  * `nome_lote`
  * `capacidade_maxima`
  * `pasto_localizacao`

* **Vacina**
  * `id_vacina` (PK - Chave Primária)
  * `nome_vacina`
  * `fabricante`
  * `periodo_validade_dias`

* **Pesagem**
  * `id_pesagem` (PK - Chave Primária)
  * `data_pesagem`
  * `peso_kg`
  * `id_animal` (FK - Chave Estrangeira)

* **Aplicacao_Vacina**
  * `id_aplicacao` (PK - Chave Primária)
  * `data_aplicacao`
  * `dose_ml`
  * `id_animal` (FK - Chave Estrangeira)
  * `id_vacina` (FK - Chave Estrangeira)

---

## 4. Diagrama Entidade e Relacionamento (DER)
# Modelo de Entidade e Relacionamento (MER) - Manejo Pecuário

## 1. Entidades

* **Animal:** Representa cada bovino individualmente na propriedade.
* **Lote:** Representa a área ou agrupamento de manejo onde o animal está alocado.
* **Vacina:** Representa o tipo de vacina/medicamento disponível no catálogo da fazenda.
* **Pesagem:** Registra a evolução do peso do animal ao longo do tempo.
* **Aplicacao_Vacina:** Registra os eventos de imunização aplicados a cada animal.  

## 2. Relacionamentos e Cardinalidades

* **[Lote] (1,1) <abriga> (0,N) [Animal]**
  * *Explicação:* Um Lote pode abrigar vários Animais (N), mas cada Animal deve estar em apenas um Lote específico por vez (1).

* **[Animal] (1,1) <registra> (0,N) [Pesagem]**
  * *Explicação:* Um Animal pode ter várias Pesagens registradas ao longo do tempo (N), mas cada Pesagem pertence obrigatoriamente a apenas um Animal específico (1).

* **[Animal] (1,1) <recebe> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Um Animal pode ter vários registros de aplicação de vacinas (N), mas cada aplicação pertence a um único Animal (1).

* **[Vacina] (1,1) <usada_em> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Uma Vacina pode ser utilizada em diversas aplicações (N), mas cada registro de aplicação refere-se a apenas um tipo de Vacina (1).

## 3. Sugestão de Atributos

* **Animal**
  * `id_animal` (PK - Chave Primária)
  * `brinco_identificacao` (Atributo Único)
  * `data_nascimento`
  * `sexo`
  * `raca`
  * `id_lote` (FK - Chave Estrangeira)

* **Lote**
  * `id_lote` (PK - Chave Primária)
  * `nome_lote`
  * `capacidade_maxima`
  * `pasto_localizacao`

* **Vacina**
  * `id_vacina` (PK - Chave Primária)
  * `nome_vacina`
  * `fabricante`
  * `periodo_validade_dias`

* **Pesagem**
  * `id_pesagem` (PK - Chave Primária)
  * `data_pesagem`
  * `peso_kg`
  * `id_animal` (FK - Chave Estrangeira)

* **Aplicacao_Vacina**
  * `id_aplicacao` (PK - Chave Primária)
  * `data_aplicacao`
  * `dose_ml`
  * `id_animal` (FK - Chave Estrangeira)
  * `id_vacina` (FK - Chave Estrangeira)

---

## 4. Diagrama Entidade e Relacionamento (DER)
# Modelo de Entidade e Relacionamento (MER) - Manejo Pecuário

## 1. Entidades

* **Animal:** Representa cada bovino individualmente na propriedade.
* **Lote:** Representa a área ou agrupamento de manejo onde o animal está alocado.
* **Vacina:** Representa o tipo de vacina/medicamento disponível no catálogo da fazenda.
* **Pesagem:** Registra a evolução do peso do animal ao longo do tempo.
* **Aplicacao_Vacina:** Registra os eventos de imunização aplicados a cada animal.  

## 2. Relacionamentos e Cardinalidades

* **[Lote] (1,1) <abriga> (0,N) [Animal]**
  * *Explicação:* Um Lote pode abrigar vários Animais (N), mas cada Animal deve estar em apenas um Lote específico por vez (1).

* **[Animal] (1,1) <registra> (0,N) [Pesagem]**
  * *Explicação:* Um Animal pode ter várias Pesagens registradas ao longo do tempo (N), mas cada Pesagem pertence obrigatoriamente a apenas um Animal específico (1).

* **[Animal] (1,1) <recebe> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Um Animal pode ter vários registros de aplicação de vacinas (N), mas cada aplicação pertence a um único Animal (1).

* **[Vacina] (1,1) <usada_em> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Uma Vacina pode ser utilizada em diversas aplicações (N), mas cada registro de aplicação refere-se a apenas um tipo de Vacina (1).

## 3. Sugestão de Atributos

* **Animal**
  * `id_animal` (PK - Chave Primária)
  * `brinco_identificacao` (Atributo Único)
  * `data_nascimento`
  * `sexo`
  * `raca`
  * `id_lote` (FK - Chave Estrangeira)

* **Lote**
  * `id_lote` (PK - Chave Primária)
  * `nome_lote`
  * `capacidade_maxima`
  * `pasto_localizacao`

* **Vacina**
  * `id_vacina` (PK - Chave Primária)
  * `nome_vacina`
  * `fabricante`
  * `periodo_validade_dias`

* **Pesagem**
  * `id_pesagem` (PK - Chave Primária)
  * `data_pesagem`
  * `peso_kg`
  * `id_animal` (FK - Chave Estrangeira)

* **Aplicacao_Vacina**
  * `id_aplicacao` (PK - Chave Primária)
  * `data_aplicacao`
  * `dose_ml`
  * `id_animal` (FK - Chave Estrangeira)
  * `id_vacina` (FK - Chave Estrangeira)

---

## 4. Diagrama Entidade e Relacionamento (DER)
# Modelo de Entidade e Relacionamento (MER) - Manejo Pecuário

## 1. Entidades

* **Animal:** Representa cada bovino individualmente na propriedade.
* **Lote:** Representa a área ou agrupamento de manejo onde o animal está alocado.
* **Vacina:** Representa o tipo de vacina/medicamento disponível no catálogo da fazenda.
* **Pesagem:** Registra a evolução do peso do animal ao longo do tempo.
* **Aplicacao_Vacina:** Registra os eventos de imunização aplicados a cada animal.  

## 2. Relacionamentos e Cardinalidades

* **[Lote] (1,1) <abriga> (0,N) [Animal]**
  * *Explicação:* Um Lote pode abrigar vários Animais (N), mas cada Animal deve estar em apenas um Lote específico por vez (1).

* **[Animal] (1,1) <registra> (0,N) [Pesagem]**
  * *Explicação:* Um Animal pode ter várias Pesagens registradas ao longo do tempo (N), mas cada Pesagem pertence obrigatoriamente a apenas um Animal específico (1).

* **[Animal] (1,1) <recebe> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Um Animal pode ter vários registros de aplicação de vacinas (N), mas cada aplicação pertence a um único Animal (1).

* **[Vacina] (1,1) <usada_em> (0,N) [Aplicacao_Vacina]**
  * *Explicação:* Uma Vacina pode ser utilizada em diversas aplicações (N), mas cada registro de aplicação refere-se a apenas um tipo de Vacina (1).

## 3. Sugestão de Atributos

* **Animal**
  * `id_animal` (PK - Chave Primária)
  * `brinco_identificacao` (Atributo Único)
  * `data_nascimento`
  * `sexo`
  * `raca`
  * `id_lote` (FK - Chave Estrangeira)

* **Lote**
  * `id_lote` (PK - Chave Primária)
  * `nome_lote`
  * `capacidade_maxima`
  * `pasto_localizacao`

* **Vacina**
  * `id_vacina` (PK - Chave Primária)
  * `nome_vacina`
  * `fabricante`
  * `periodo_validade_dias`

* **Pesagem**
  * `id_pesagem` (PK - Chave Primária)
  * `data_pesagem`
  * `peso_kg`
  * `id_animal` (FK - Chave Estrangeira)

* **Aplicacao_Vacina**
  * `id_aplicacao` (PK - Chave Primária)
  * `data_aplicacao`
  * `dose_ml`
  * `id_animal` (FK - Chave Estrangeira)
  * `id_vacina` (FK - Chave Estrangeira)

---

## 4. Diagrama Entidade e Relacionamento (DER)  
<img width="1021" height="479" alt="image" src="https://github.com/user-attachments/assets/5409a857-5d0d-4d44-a58e-d4800d274808" />


