# SQL

---

## Примеры запросов
### SELECT
```sql
SELECT [ALL | DISTINCT] <список_выбора>
FROM <имя_таблицы>, ...
[ WHERE <условие> ]
[ GROUP BY <имя_столбца>,... ]
[ HAVING <условие> ]
[ORDER BY <имя_столбца> [ASC | DESC],... ]
```
### UPDATE
```sql
UPDATE таблица 
SET { поле=значение } [,...] 
[ { WHERE условие } ]
```
### DELETE
```sql
DELETE FROM таблица 
[ WHERE условие ]
```
### INSERT
```sql
INSERT INTO таблица 
[ ( поле [,...] ) ]
{ VALUES ( Wertliste [,...] ) } 
```
### CREATE TABLE
```sql
CREATE [TEMPORARY] TABLE [IF NOT EXISTS]
tbl_name [(create_definition,...)] 
[table_options] 
[select_statement]
```
### DROP TABLE
```sql
DROP TABLE [IF EXISTS] tbl_name [, tbl_name,...] [RESTRICT | CASCADE]
```

---

## JOINы
![Виды JOIN'ов](Resource/sql_join.png)

### Inner join
Самый простой вид соединения INNER JOIN – внутреннее соединение. 
Этот вид джойна выведет только те строки, если условие соединения выполняется (является истинным, т.е. TRUE). 
В запросах необязательно прописывать INNER – если написать только JOIN, то СУБД по умолчанию выполнить 
именно внутреннее соединение.

### Left и right join
Левое и правое соединения еще называют внешними. 
Главное их отличие от внутреннего соединения в том, что строка из левой (для LEFT JOIN) или из правой таблицы 
(для RIGHT JOIN) попадет в результаты в любом случае.

### Full join
Этот вид джойна вернет все строки из всех таблиц, участвующих в соединении, соединив между собой те, 
которые подошли под условие ON.
