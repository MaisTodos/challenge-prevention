# Descrição do caso
Um grupo empresarial de vendas de eletrodomésticos com extensão nacional possui milhares de *Parceiros Comerciais* filiados que compram os produtos da sede e realizam a venda destes. Durante uma campanha de marketing de fim de ano, a sede definiu metas de vendas com premiações para todos os *Parceiros Comerciais*(PCs) com base no volume de vendas durante o **mês de março de 2024**.

No fechamento da campanha foi observado que vários desses *PCs* fizeram vendas de eletrodomésticos com valores muito abaixo dos definidos pela matriz. O preço mínimo de um eletrodoméstico no catálogo seria de R$100,00 e mesmo assim tiveram vendas de R$10,00 e até R$5,00.

Para realizar a análise temos como base uma base de dados SQLite (historico_diario.db) que possui duas tabelas. Uma tabela em SQL contendo os lançamentos de vendas de todas os *PCs* chamada **fechamento_campanha**. Esta tabela possui somente as colunas de:

- **id_nome**: nome-único do *PC*; 
- **n_vendas**: número total de vendas do *PC*;

Existe também uma tabela contendo o histórico de fechamentos de caixa de todas as PCs, com o valor total vendido no dia em cada PC. As colunas dessa tabela são:
- **fechamento_id**: chave primária com o id do fechamento (auto_increment); 
- **valor_diario**: o valor total diário de vendas do *PC* em reais;  
- **nome_pc**: nome-único do *PC*;
- **data_fechamento**: data e hora do fechamento de caixa no formato (YYYY-MM-DD HH:mm:ss);

# Exemplo das tabelas
## Tabela de resultado da campanha de Março/2024 (fechamento_campanha)
|  id_nome  | n_vendas |
|--------|----------|
| $PC_1$ | 5000     |
| $PC_2$ | 10000    |
| $PC_3$ | 40000    |

## Tabela histórica de fechamentos de caixa diários (historico_diario)
| fechamento_id | nome_pc   | valor_diario | data_fechamento     |
|---------------|-----------|--------------|---------------------|
| ...           | ...    | ...          | ... |
| 101           | $PC_1$    | 100          | 2022-03-01 23:59:02 |
| 102           | $PC_2$    | 100          | 2022-03-01 23:59:05 |
| ...           | ...    | ...          | ... |
| 466           | $PC_1$    | 100          | 2024-03-01 23:59:00 |
| 467           | $PC_2$    | 200          | 2024-03-01 23:59:01 |
| 468           | $PC_3$    | 400          | 2024-03-01 23:59:10 |
| 469           | $PC_1$    | 300          | 2024-03-02 23:59:10 |
| 470           | $PC_2$    | 299          | 2024-03-02 23:59:19 |
| 471           | $PC_3$    | 599          | 2024-03-02 23:59:18 |

# Objetivo
Nesse caso não houve nenhum dano financeiro à matriz pois o fechamento de caixa ficou igual o valor transacionado, no entanto a campanha foi prejudicada. O intuito desta investigação post-mortem é:
- Analisar o volume de vendas: Desenvolver um código SQL que traria os possíveis casos de vendas falsificadas;
- Comparar as vendas desse ano (2024) com as do ano passado (2023): Desenvolver código SQL que faria essa comparação;
- Entender o objetivo dessas vendas;
- Sugerir mudanças do processo, tanto para impedir fraudes quanto para fazer novas campanhas de marketing;
- Sugerir monitoramentos possíveis para evitar estes casos no futuro.

# Perguntas
## No que serei avaliado?
- Olhar crítico da situação;
- Compreensão de casos de fraude;
- Desenvolvimento de queries SQL; 
- Sugestões de melhoria de processo e de monitoramento;
- Criatividade: caso tenha alguma solução ou sugestão que não foi abordada no case, sinta-se a vontade para desenvolver.

## O código precisa rodar no arquivo de banco de dados disponibilizado?
Não, o arquivo disponibilizado é para que você teste o que fez. Não vamos rodar seus códigos, a explicação do seu processo para construção da solução é o que estamos interessados. 

## Terei a chance de explicar minhas decisões?
Sinta-se à vontade para comentar seu processo. Discutiremos as escolhas que você fez na entrevista.
