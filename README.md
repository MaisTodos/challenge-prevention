# Descrição do caso
Um grupo empresarial de vendas de eletrodomésticos com extensão nacional possuí milhares de *Parceiros Comerciais* filiados que compram os produtos da sede e realizam a venda destes . Durante uma campanha de marketing de fim de ano, a sede definiu metas de vendas com premiações para todos os *Parceiros Comerciais*(PCs) com base no volume de vendas. Basear-se no volume de vendas não seria um problema a príncipio, pois os eletrodomésticos possuem valor próximo, no entanto, em análise do fechamento da campanho, foi observado que vários desses *PCs* fizeram vendas de eletrodomésticos com valores muito abaixo dos definidos pela matriz. O preço mínimo de um eletrodoméstico no catálogo seria de R$100.00 e mesmo assim tiveram vendas de R$10.00 e até R$5.00.

Para realizar a análise temos como base uma tabela em SQL contendo os lançamentos de vendas de todas os *PCs* chamada **tabela_transacional** esta tabela possui as colunas de:

- **nome**: chave primária o nome-único do *PC*; 
- **valor_total**: o valor total de vendas do *PC*;  
- **n_vendas**: número total de vendas do *PC*;

# Exemplo da tabela
| nome   | valor_total | n_vendas |
|--------|-------------|----------|
| $PC_1$ | 1000        | 800      |
| $PC_2$ | 10000       | 100      |
| $PC_3$ | 10000       | 10000    |

# Objetivo
Nesse caso não houve nenhum dano financeiro à matriz pois o fechamento de caixa ficou igual o valor transacionado, no entanto a campanha foi prejudicada. O intuito desta investigação post-mortem é:
- Analisar o volume de emissão desses cashbacks: Desenvolver um código SQL que traria os possíveis casos de vendas falsificadas, isto é, $valor\\_total/n\\_vendas$ menor que R$90.00;
- Entender o objetivo dessas emissões: nosso time imagina que seja para fraudar a campanha, consegue imaginar algum outro objetivo, para essas falsificações de vendas?
- Sugerir mudanças do processo, tanto para impedir essas fraudes quanto para fazer uma nova campanha de marketing nesse mesmo sentido;
- Sugerir monitoramentos possíveis para evitar esses casos no futuro.

# Perguntas
## No que serei avaliado?
Olhar crítico da situação, compreensão de casos de fraude, desenvolvimento de queries SQL, sugestões de melhoria de 
processo e de monitoramento.

## Terei a chance de explicar minhas decisões?
Sinta-se à vontade para comentar seu processo. Discutiremos as escolhas que você fez na entrevista.
