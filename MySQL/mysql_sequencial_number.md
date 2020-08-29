# Criando sequencia de números 

## Solução para o Mysql 
Considerando que a numeração possa ser volátil, e que o MySQL não tem um contador de linhas por padrão, segue uma query que supre a contagem usando @variáveis:
```sql
SET @contador := 0;
SELECT
   @contador := @contador + 1 AS linha,
   t.campo1,
   t.campo2
FROM
   tabela t
```
Se por alguma razão não puder fazer o SET separado:

```sql
SELECT
   @contador := @contador + 1 AS linha,
   t.campo1,
   t.campo2
FROM
   (SELECT @contador := 0) AS nada,
   tabela t
```
E se quiser numerar o resultado de uma Query complexa

```sql
SELECT
   @contador := @contador + 1 AS linha,
   t.campo1,
   t.campo2
FROM
   (SELECT @contador := 0) AS nada,
   (SELECT SUM(campo) FROM tabela GROUP BY algumacoisa JOIN outracoisa ... ) AS t
```

> Não chega a ser uma reordenação de chave primária, mas se for apenas para numeração de linhas, creio que resolva. Nesta outra resposta apliquei o mesmo conceito para paginação de resultados, com um exemplo de como fazer a mudança do valor inicial do índice conforme as páginas.

Veja aplicado ao [SQL Fiddle](http://sqlfiddle.com/#!2/3e75e7).

## Solução para T-SQL:
Em T-SQL fica mais fácil, já tem função pronta pra isso:

```sql
SELECT
   ROW_NUMBER() OVER (ORDER BY campo1),
   t.campo1,
   t.campo2
FROM
   tabela t
```

[Fonte: stackoverflow](https://pt.stackoverflow.com/questions/43888/numera%C3%A7%C3%A3o-sequencial-dos-resultados-de-uma-query) 