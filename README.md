# Sistema de Manejo Pecuário  

## Descrição de Minimundo  
* Pequenas e médias propriedades rurais dedicadas à pecuária de corte e cria enfrentam grandes desafios operacionais ao gerenciar seu rebanho de forma manual, por meio de cadernos de campo ou planilhas isoladas. A ausência de  um sistema centralizado e confiável provoca falhas críticas no dia a dia da fazenda: perda de prazos no calendário sanitário obrigatório,superlotação de pastagens(o que degrada o solo e reduz o ganho de peso do gado), dificuldade na rastreabilidade individual de cada animal, desconhecimento sobre a real conversão alimentar e falta  de precisão no controle financeiro das vendas e perdas do plantel.
  
   Para superar essas dificuldades, o Sistema de Manejo Pecuário foi projetado para informatizar e integrar toda a gestão zootécnica, sanitária e comercial da propriedade rural. O funcionamento do sistema abrange desde a organização física da fazenda até a saída final dos animais:

 * Divisão Territorial e Lotação (Pastos e Lotes): A propriedade é dividida em áreas físicas chamadas Pastos (invernadas ou piquetes), onde são controlados o nome da área, o tamanho em hectares e o tipo de capim cultivado (como Brachiaria, Mombaça ou Tifton). Para otimizar o manejo nutricional e reprodutivo, o rebanho é agrupado em Lotes específicos por categoria ou objetivo produtivo (ex.: Bezerros Desmamados, Matrizes, Garrotes em Engorda ou Isolamento Sanitário), respeitando a capacidade máxima de cada lote e sua alocação em um determinado pasto.

* Rastreabilidade Individual (Animais): Cada bovino que nasce ou ingressa na fazenda recebe um brinco de identificação único e intransferível. O sistema armazena sua ficha completa contendo data de nascimento, sexo, raça, lote atual e status dentro da propriedade (Ativo, Vendido ou Morto), garantindo histórico individualizado durante todo o ciclo produtivo.

* Controle Sanitário e Imunização (Vacinas e Aplicações): A fazenda mantém um catálogo atualizado de Vacinas e medicamentos veterinários, registrando o nome comercial, o fabricante e o período de validade em dias. Sempre que ocorre uma campanha de vacinação ou tratamento preventivo, o sistema registra o evento de Aplicação de Vacina, vinculando o animal, a vacina utilizada, a data exata da aplicação e a dosagem administrada em mililitros (ml), evitando tanto a duplicidade de doses quanto o esquecimento de animais.

* Acompanhamento Zootécnico (Pesagens): Periodicamente, os animais passam pelo tronco de contenção e balança digital. Cada Pesagem é registrada com a data da medição e o peso em quilogramas (kg), permitindo ao produtor acompanhar a curva de crescimento, calcular o Ganho Médio Diário (GMD) e identificar o ponto ideal de abate ou reprodução.

* Saída do Rebanho (Vendas e Óbitos): O ciclo do animal na propriedade encerra-se de duas formas. Na operação comercial, o produtor realiza Vendas para frigoríficos ou outros pecuaristas, registrando a data da negociação, o comprador, o valor total da transação e vinculando todos os animais incluídos naquele lote comercializado. Por outro lado, caso ocorra alguma fatalidade na fazenda (como acidentes ofídicos, doenças ou complicações climáticas), o sistema permite o registro formal do Óbito vinculado exclusivamente àquele animal, documentando a data, o motivo da perda e as observações veterinárias para auditoria do rebanho.
## Regras de Negócio  
1. **Gestão de Pastagens:** A fazenda é dividida em pastos, cada um identificado por nome, tamanho em hectares e tipo de pastagem predominante.
2. **Alocação de Lotes:** Um pasto pode comportar vários lotes ao longo do tempo, mas cada lote de manejo (ex.: *"Lote Desmama"*, *"Lote Boi Gordo"*) está alocado em apenas um pasto por vez, respeitando sua capacidade máxima.
3. **Identificação Individual:** Cada animal deve ser cadastrado individualmente com um brinco de identificação único, informando data de nascimento, sexo (`M` ou `F`), raça e status atual (`Ativo`, `Vendido` ou `Morto`).
4. **Pertencimento a Lote:** Todo animal pertence obrigatoriamente a um único lote por vez, enquanto um lote pode abrigar diversos animais.
5. **Controle Sanitário (Vacinação):** Um animal pode receber várias aplicações de vacinas ao longo da vida, e uma mesma vacina do catálogo pode ser aplicada em diversos animais. Cada aplicação deve registrar a data e a dose em mililitros (`ml`).
6. **Acompanhamento de Peso:** Um animal passa por diversas pesagens periódicas na balança para controle de desenvolvimento, registrando a data e o peso em quilogramas (`kg`) de cada medição.
7. **Baixas por Venda ou Óbito:** Uma transação de venda pode englobar um ou vários animais (registrando data, comprador e valor total). Em caso de falecimento na propriedade, registra-se no máximo um óbito por animal, contendo a data, o motivo e a observação veterinária.

## Diagramas do Projeto
* **Modelo Conceitual (DER):** <img width="969" height="710" alt="Captura de tela 2026-11-24 085903" src="https://github.com/user-attachments/assets/0227adc9-0c6a-4b69-8403-49a070e6006d" />

* **Modelo lógico/ físico (EER Workbench):** <img width="626" height="843" alt="Captura de tela 2026-11-24 093953" src="https://github.com/user-attachments/assets/eae62963-d3a0-4621-8b7f-d23acd10a0f1" />

  
## Scripts SQL 
* **Estrutura do Banco(DDL):**[script.ddl.sql](https://github.com/user-attachments/files/35331463/script.ddl.sql)
 
* **Povoamento de Dados por Cenários (DML):** [script.dml.sql](https://github.com/user-attachments/files/35331488/script.dml.sql)



