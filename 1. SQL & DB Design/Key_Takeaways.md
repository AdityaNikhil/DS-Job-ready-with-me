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

