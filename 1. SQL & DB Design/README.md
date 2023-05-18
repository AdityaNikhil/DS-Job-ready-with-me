# Key Takeaways
Here I'll be covering all the points that I found useful and important to remember for future references. 

### Track 2
1. Benefits of **filtering data**, 
   1. Reduce the time it takes to run the query
   2. Reduces the strain on the client application
   3. Removes unwanted data in a calculation
   4. Helps you understand the contents of your data
   5. Narrows down the results of the data. 

2. **Wildcards** take longer to run compared to logical operators. 

   - They cannot be used for non-text data items.
   - Wildcards at the end of search patters take longer to run.

3. `ORDER BY` clause can take the name of one or more columns to sort.

   

   **Example:**

   

   ```sql
   CREATE TABLE alph_num (
   
    alphabets TEXT NOT NULL,
   
    numbers INT NOT NULL
   
   );
   
   INSERT INTO alph_num VALUES ('a', 5);
   
   INSERT INTO alph_num VALUES ('b', 6);
   
   INSERT INTO alph_num VALUES ('c', 7);
   
   INSERT INTO alph_num VALUES ('d', 8);
   
   INSERT INTO alph_num VALUES ('e', 9);
   
   INSERT INTO alph_num VALUES ('f', 12);
   
   INSERT INTO alph_num VALUES ('f', 11);
   
   INSERT INTO alph_num VALUES ('f', 10);
   
   
   SELECT * FROM alph_num ORDER BY alphabets DESC, numbers ASC; 
   ```

   **Output**

   ```
   f|10
   f|11
   f|12
   e|9
   d|8
   c|7
   b|6
   a|5
   ```

   As you can see, it first sorts the alphabets column in desc order and then sorts only the matching records in numbers column in asc order. 

   

   *There are 3  matching 'f' records with 3 different numeric values in numbers column that are sorted in ascending order.*
   
   
### Track 3
   1. Joins tend to execute faster. In fact, query retrieval time using joins will almost always outperform one that employs a subquery. The reason is that joins mitigate the processing burden on the database by replacing multiple queries with one join query. 
[Source](https://www.navicat.com/company/aboutus/blog/1704-joins-versus-subqueries-which-is-faster#:~:text=I%20won't%20leave%20you,queries%20with%20one%20join%20query.)
   2. There is no limit to the number of table you can join with an inner join.
   3. Inner joins are one of the most popular types of joins use.
   4. Performance will most likely worsen with the more joins you make.
   
   <img src='https://shipengfei92.github.io/assets/img/joins.png' width='500' height='300'>
   
   *Source: Coursera*
   
   **UNIONS**
   1. The columns must also have similar data types
   2. The UNION operator is used to combine the result-set of two or more SELECT statements
   3. Each SELECT statement within UNION must have the same number of columns


### Track 4
**Concatenating example:**
```
SELECT CONCAT(col1, col2) FROM table1;
out:
col1_1 col3_1
col1_2 col3_2
```
*Or you can use '||' or '+' which is used in SQL Server.*

**Substring example:**
```
SELECT FirstName, SUBSTR(val, val_pos, total_chars) FROM table1;
SELECT FirstName, SUBSTR(FirstName, 2, 4) FROM table1;

out:
Aditya dity
```
**Datetime:**

Datetimes varies with every database. So it's a good practice to look up   for the date type of that specific dbms.

**CASE:**

CASE can be used in SELECT, INSERT, UPDATE and DELETE stmts.


