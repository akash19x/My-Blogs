## Some simple ways to optimize your SQL query

This blog will focus mainly on some simple ways in which we can optimise our SQL query. We shall see some good examples where just choosing the other way to write the same query can make a huge impact on performance.

> 
Query optimization is the overall process of choosing the most efficient means of executing a SQL statement.

### Why is it needed?

- First, it provides the user with faster results, which makes the application seem faster to the user.
- Secondly, it allows the system to service more queries in the same amount of time, because each request takes less time than unoptimized queries.
- Thirdly, query optimization ultimately reduces the amount of wear on the hardware (e.g. disk drives), and allows the server to run more efficiently (e.g. lower power consumption, less memory usage).

### Basic steps in query processing

![Screenshot from 2021-12-15 15-02-10.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639560760057/i--s80j15.png)

1. **Query :** A query is a request for information from a database. 

2. **Parser and Translators :** The query which is written in sql form is parsed and translated in this step into **relational algebra expression** so that the device can work with that.

3. **Optimizer : ** In this step, the expression is optimised by making use of information like : what are the attributes on which more often where conditions are put? how many tuples are there in a regular expression? and so on... 
> 
Optimization needs to consider an immense number of possible moves as quickly as possible, remove the poor choices, and finish with the best possible move.

4. **Execution Plan : ** Based on the optimizer, an execution plan is decided i.e., how we actually want to do this, in terms of accessing the different indexes and different B+ tree nodes etc to evaluate the query and that is the job of the **evaluation engine** as we can see uses data for that.
> Execution is the final step. SQL Server takes the execution plan that was identified in the optimization step and follows those instructions in order to execute the query.

5. After following all these steps, the query output is generated.

### Some better ways to write simple sql queries for optimisation :

1. The sql query becomes faster if we use the actual columns names in SELECT statement instead of Select ALL. 
<br>For Example: Write the query as<br>
```SELECT id, first_name, last_name, age, subject FROM student_details;
``` <br>
This is a good practice to specify only the columns that we need in select query instead of **SELECT * ** in order to avoid extra load on the database.

2. HAVING clause is used to filter the rows after all the rows are selected. It is just like a filter. Do not use HAVING clause for any other purposes.<br>
Write query as : <br>
![carbon (13).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639563212640/0cJHn7sOi.png)
Instead Of : 
![carbon (14).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639563260985/R6SkMU8za.png)
Having is actually a filter to filter out rows after all the rows are selected and should be used for that purpose only.

3.  **Try to avoid correlated sub queries**<br><br>
A correlated subquery depends on the parent or outer query. Since it executes row by row, it decreases the overall speed of the process.<br>
**Inefficient : **
![carbon (15).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639563627851/MiDMLmFaF.png)
Here, the problem is — the inner query is run for each row returned by the outer query. Going over the “company” table again and again for every row processed by the outer query creates process overhead. Instead, for SQL query optimization, use JOIN to solve such problems.<br><br>
**Efficient : **
![carbon (16).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639563735354/lEuerB7-p.png)

4. Use operator EXISTS, IN and table joins appropriately in your query.<br>
a) Usually IN has the slowest performance.<br>
b) IN is efficient when most of the filter criteria is in the sub-query.<br>
c) EXISTS is efficient when most of the filter criteria is in the main query.<br>
For example, write query as : 
![carbon (17).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639563894632/SXMftVq6m.png)
Instead of :
![carbon (18).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639563920923/4BGKAhGL8.png)

5. Exists vs COUNT?<br>
Normally, developers use EXITS() or COUNT() queries for matching a record entry. However, EXISTS() is more efficient as it will exit as soon as finding a matching record; whereas, COUNT() will scan the entire table even if the record is found in the first row.<br><br>
**Inefficient :**
![carbon (19).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639564062805/wYVyA9p4d.png)
**Efficient : **
![carbon (20).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639564100120/rswzG480A.png)

6. Try to use UNION ALL in place of UNION.<br>
**a)** Union operator removes all the duplicate records whereas Union All does not therefore Union All is a faster operation as it does not have to do the additional work of removing duplicate rows.<br>
**b)** We should only use Union when removing duplicate rows is a priority.

7. Avoid running queries in a loop<br>
Coding SQL queries in loops slows down the entire sequence. Instead of writing a query that runs in a loop, you can use bulk insert and update depending on the situation. <br>Suppose there are 1000 records. Here, the query will execute 1000 times.<br><br>
**Inefficient : **
![carbon (21).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639564549184/tLSEu1IgX.png)
**Efficient : **
![carbon (22).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1639564587579/Q6vju0Pr3.png)

### Conclusion

With these simple steps we can optimise our sql query for the most basic operations we use. Of course, there is more to this as this is an introduction to some query optimisation for those who are new to this topic and want to play with simple queries. <br>

Thanks for reading. 😇 I'll be posting much more content of python,sql and data science in my coming blogs.




























