# Modelo de Entidade e Relacionamento (MER) - Manejo Pecuário

## 1. Entidades
* **Pasto:** Representa a área física da fazenda onde os lotes de animais são alocados.
* **Animal:** Representa cada bovino individualmente na propriedade.
* **Lote:** Representa o agrupamento de manejo onde o animal está alocado.
* **Vacina:** Representa o tipo de vacina/medicamento disponível no catálogo da fazenda.
* **Pesagem:** Registra a evolução do peso do animal ao longo do tempo.
* **Aplicação_Vacina:** Registra os eventos de imunização aplicados a cada animal.
* **Venda:** Registra a transação comercial ou nota de venda referente à saida de um grupo de animais da propriedade.
* **Obito:** Registra a ocorrência e causa da morte de um animal especifico.

## 2. Relacionamentos e Cardinalidades

* **[Pasto] 1 (possui) n [Lote]**
* *explicação:* Um pasto possui vários lotes ao longo do tempo (N), mas cada lote fica alocado em apenas um pasto específico por vez (1).
  
* **[Lote] 1 (abriga) n [Animal]**
  * *Explicação:* Um Lote pode abrigar vários Animais (N), mas cada Animal deve estar em apenas um Lote específico por vez (1).

* **[Animal] 1 (registra) n [Pesagem]**
  * *Explicação:* Um Animal pode ter várias Pesagens registradas ao longo do tempo (N), mas cada Pesagem pertence obrigatoriamente a apenas um Animal específico (1).

* **[Animal] n (recebe) n [Vacina]**
  * *Explicação:* Um Animal recebe diversas Vacinas ao longo do tempo (N), e uma mesma vacina do catálogo é aplicada em diversos Animais(N).
  * *implementação:* Este relacionamento é resolvido através da entidade associativa Aplicação_Vacina, que conecta as FKs de Animal e Vacina juntamente com os atributos data_aplicação e dose_ml.
    
* **[Venda] 1 (inclui) n [Animal]**
  * *Explicação:* Uma transação de venda engloba uma ou mais unidades de Animais(N). Cada Animal pertence a no máximo uma Venda(1).
    
* **[Animal] 1 (registra_morte) 1 [óbito]**
  * *Explicação:* Um animal registra no máximo um óbito em todo o seu ciclo (1). Cada registro de óbito refere-se exclusivamente a único Animal(1).

## 3. Sugestão de Atributos

* **Pasto**
  * `id_pasto` (PK - Chave Primária)
  * `nome_pasto`
  * `area_hectares`
  * `tipo_capim`
  
* **Animal**
  * `id_animal` (PK - Chave Primária)
  * `brinco_identificacao` (Atributo Único)
  * `data_nascimento`
  * `sexo`
  * `raca`
  * `status (ex:ativo/vendido/morto`
  * `id_lote` (FK - Chave Estrangeira)
  * `id_venda` (FK - Chave estrangeira referente a venda, nula enquanto o animal estiver na fazenda)

* **Lote**
  * `id_lote` (PK - Chave Primária)
  * `nome_lote`
  * `capacidade_maxima`
  * `pasto_localizacao`
  * `id_pasto` (FK - chave estrangeira referente a pasto)

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

 * **Venda**
   * `id_venda` (PK - chave primaria)
   * `data_venda`
   * `comprador`
   * `valor_total`

  * **Óbito**
    * `id_obito` (PK - Chave estrangeira)
    * `data_obito`
    * `motivo`
    * `id_animal` (FK - chave estrangeira)
## 4. Diagrama Entidade e Relacionamento (DER) 




<img width="640" height="482" alt="image" src="https://github.com/user-attachments/assets/890a3b19-d8d3-43ff-b6ea-e5b6061a7684" />




