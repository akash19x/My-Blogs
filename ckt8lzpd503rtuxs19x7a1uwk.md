## Python database connectivity and performing manipulations.

Python have a range of libraries and functions which can help us perform various data manipulations on tables. In this blog, I am going to show how we can connect our database with python using **SQLAlchemy** library and then perform data manipulation (reading, updating, inserting and deleting data) using **pandas**.

The various operations which we will be performing are :

1. **Establishing database connection in Python**

2. **Reading the data from table**

3. **Read data as query**

4. **Inserting a new row with python and writing back to database**

5. **Drop the table**

### 1- Establishing database connection
I'm going to use sqlalchemy library which is the Python SQL toolkit and Object Relational Mapper that gives application developers the full power and flexibility of SQL.
I'm going to use **postgresql ** as my database but we can use any type of connection strings to establish connections.

Some connection strings :

postgresql : ``` 'postgresql://username:password@localhost:port/database_name' ``` 

oracle : ``` 'oracle://username:password@localhost:port/database_name' ``` 

mysql: ``` 'mysql+pymysql://username:password@localhost:port/database_name' ``` 

**Code Snippet : **

![carbon (6).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630925532642/LfcHnab-0.png)

### 2- Reading the data from table

Pandas has a function : **pd.read_sql_table**("table_name",engine) which takes in the table name which we want to read and our connection engine and it returns the table as a dataframe.


![Screenshot from 2021-09-06 16-26-23.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630925818872/HsAwhRBlj.png)

### 3- Read data as query
Pandas has a function : **pd.read_sql**("table_name/query",engine) which takes in the table name or sql query which we want to read and our connection engine and it returns the table as a dataframe.
This function is a convenience wrapper around read_sql_table and read_sql_query.

Ex- : Suppose we want to read a join of two tables, we can perform this operation by reading a query instead of one single table.

![Screenshot from 2021-09-06 17-27-57.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630929499904/JVs4ZgHue.png)

### 4- Inserting a new row with python

Pandas has a function **df.to_sql()** which writes records stored in a dataframe to a SQL database.
The corresponding tables can be newly created, appended to, or overwritten.


![Screenshot from 2021-09-06 16-49-00.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630927319461/OlTRzGpNH.png)

Let's confirm this entry by querying our database.


![Screenshot from 2021-09-06 16-53-08.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630927405267/Ds0g2Fvga.png)

That's how we can perform Insert a row operation directly into the database. We can also perform update and delete operations as well just by manipulating our dataframe. 

### 5- Drop the table

We can  create a cursor from our SQLAlchemy engine and execute our drop table command as shown in this code snippet. 

![carbon (7).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630930011245/5BpNfjWGp.png)


## Conclusion
This is an introduction to how one can connect the database with python and perform data manipulation.  I'll be posting much more content of python and data science in my coming blogs.

Thanks for your time! :)
