##### Não tinha a tabela, pois o exercício não disponibiliza ela por isso a maioria das respostas estão diferentes do pedido mas com a mesma lógica aplicada.

Chegou a hora de se desafiar a desenvolver ainda mais todo o conhecimento aprendido durante nossa jornada!

Aqui estão algumas atividades que vão te ajudar a praticar e fixar ainda mais cada conteúdo e caso você precise de ajuda, opções de solução das atividades estão disponíveis na seção **Opinião da pessoa instrutora**.

Abaixo estão 10 exercícios de SQL que abrangem uma variedade de tópicos, desde funções de agregação e string até operadores lógicos e cláusulas de filtragem. **Esses exercícios são projetados para serem aplicados em um banco de dados genérico** e podem precisar de ajustes para se adequarem a esquemas específicos.

1. Selecione os primeiros 5 registros da tabela `clientes`, ordenando-os pelo nome em ordem crescente. 
```SQL
SELECT * from Colaboradores ORDER by nome ASC LIMIT 5;
```
2. Encontre todos os produtos na tabela `produtos` que não têm uma descrição associada (suponha que a coluna de descrição possa ser nula).
```SQL
SELECT * from HistoricoEmprego WHERE datatermino is NULL;
```
3. Liste os funcionários cujo nome começa com 'A' e termina com 's' na tabela `funcionarios`.
```SQL
SELECT * from colaboradores where nome like 'A%' and nome like '%s';
```
4. Exiba o departamento e a média salarial dos funcionários em cada departamento na tabela `funcionarios`, agrupando por departamento, apenas para os departamentos cuja média salarial é superior a $5000.

```sql
SELECT cliente, AVG (total_do_pedido) as media from tabelapedidos2 GROUP by status HAVING media > 50;
```

5. Selecione todos os clientes da tabela `clientes` e concatene o primeiro e o último nome, além de calcular o comprimento total do nome completo.
```SQL
SELECT (nome || parentesco) as tamanho, LENGTH(nome || parentesco) from Dependentes ;
```
6. Para cada venda na tabela `vendas`, exiba o ID da venda, a data da venda e a diferença em dias entre a data da venda e a data atual.

```SQL
SELECT id, data_do_pedido, JULIANDAY (data_de_envio_estimada) - JULIANDAY (data_do_pedido) FROM tabelapedidos2 ;
```

7. Selecione todos os itens da tabela `pedidos` e arredonde o preço total para o número inteiro mais próximo.

```SQL
SELECT *, FLOOR (total_do_pedido) FROM tabelapedidos2;
```

8. Converta a coluna `data_string` da tabela `eventos`, que está em formato de texto (YYYY-MM-DD), para o tipo de data e selecione todos os eventos após '2023-01-01'.

```sql
SELECT DATE(data_de_envio_estimada) as datass FROM tabelapedidos2 where datass> '2023-09-00' ORDER by datass;
```

9. Na tabela `avaliacoes`, classifique cada avaliação como 'Boa', 'Média', ou 'Ruim' com base na pontuação: 1-3 para 'Ruim', 4-7 para 'Média', e 8-10 para 'Boa'.

```sql
SELECT lucro_liquido, 
CASE
WHEN lucro_liquido < 20000 THEN 'baixo'
WHEN lucro_liquido BETWEEN 20000 and 40000 THEN 'medio'
ELSE 'alto'
end as categorias_faturamento
from faturamento;
```

10. Altere o nome da coluna `data_nasc` para `data_nascimento` na tabela `funcionarios` e selecione todos os funcionários que nasceram após '1990-01-01'.

```sql
alter table Dependentes RENAME COLUMN datanascimento to data_nasc;
SELECT data_nasc from Dependentes where data_nasc > '1990-01-01';
```

