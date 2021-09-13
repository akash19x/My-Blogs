## 10 Common SQL operations to perform using Pandas

One of the key features of being a data analyst is to query the data from files, databases etc to perform some data manipulation or visualisation and sometimes it's much better if we can do it directly through code instead of looking into the database tables over and over again.
**Pandas** is a python library which can store query results in variables called "**dataframes"** and it helps us to perform data manipulations, visualisation and can convert our results back in the databases or files as write operations.

This blog basically describes how one can use 10 basic SQL operations using the pandas library.
### Dataset which we'll be using as an example :
 **We will use two datasets :**
- Marks of various students in 3 subjects. (Primary keys : class and roll_no)

![Screenshot from 2021-08-21 14-36-31.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629537007599/FoWJLvTI9.png)

- Personal details of students. (Primary keys : class and roll_no)

![Screenshot from 2021-08-21 14-37-58.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629537039557/WUPPrMHjw.png)

### 1. Selecting the data

- In sql we can select the data of various columns using this querry :<br>
```SELECT name,roll_no,phone FROM student_details;
``` 
- This is how it's done in pandas : 

![Screenshot from 2021-08-21 15-25-01.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629539728388/EHGLD5MFu.png)

### 2. Using aggregate functions 
- Now let's find the maximum marks a student of class 7th got in maths<br>
```SELECT max(maths) FROM student_marks WHERE class=7;
``` <br>
- Pandas has several functions like min(),max(),mean() etc that works on a column, which one can use to achieve the above operation

![Screenshot from 2021-08-21 16-07-12.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629542443941/i_qEGMbEk.png)
 
### 3. Order By clause
- This clause in SQL is used for sorting the values in ascending or descending order
   **Query to sort names in ascending order :  **<br>
   ```select * from student_details order by name;```

   **Query to sort names in descending order :  **<br>
   ```select * from student_details order by name desc;``` 

-  In pandas we can do the same with df.sort_values() function
   This function takes in 'column_to_be_sorted', ascending = True for ascending order and ascending = False for descending order sorting.

![Screenshot from 2021-08-21 16-27-39.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629543518632/Q27HQNKAD.png)

### 4. Group By clause
- Let's count the number of students in different classes<br>
   ```select class,count(*) from student_details group by class;```

![Screenshot from 2021-08-21 19-52-50.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629555799614/JJtTYH5YJ.png)

-  In pandas we can do the same with **df.groupby()** function

![Screenshot from 2021-08-22 12-24-37.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629615302878/JhPXlyAsv.png)

### 5. IN and NOT IN
- Let's select only those rows where blood group is A or B<br>
   ```select * from student_details where blood_group in ('A', 'B') ;```

-  In pandas we can do the same with isin() which works on a particular colum
   
![Screenshot from 2021-08-21 20-03-11.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629556467968/cIvHQWU95.png)
-  For **NOT IN** we can just add a negation symbol "~" in the pandas condition :

![Screenshot from 2021-08-21 20-06-09.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629556586211/lYWD5stbo.png)

### 6. Joins
- Join statement to get all the details and marks of students together<br>
   ```SELECT * from student_details a JOIN student_marks b ON (a.roll_no=b.roll_no AND a.class=b.class); ```

-  In pandas we can do the same using merge() function and
    we can specify the type of join like inner,outer,left,right as well.
   
![Screenshot from 2021-08-21 22-00-23.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629563460804/LZft2PGsO.png)


### 7. Creating new column using existing ones
- Now, let's add a new column total which adds marks in 3 subjects for each student<br>
   ```SELECT class,roll_no,science,maths,english,science+maths+english as total FROM student_marks;```

-  Just add df['new_column'] and fill it's value using other columns or with their operations

![Screenshot from 2021-08-21 22-07-13.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629563977920/cDb9tSVZh.png)
### 8. Selecting data conditionally
- Let's try filtering the data using multiple conditions.<br>
   ```select * from student_details where class=7 and gender='M' and blood_group='O';```

-  We can provide multiple conditions in braces () followed by AND (&) or OR (|)

![Screenshot from 2021-08-21 22-14-38.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629564371145/FOR1MdsNa.png)

### 9. Insert and Update 
- **Inserting** a new row in student_details table : <br>
   ```insert into student_details(name,roll_no,class,gender,blood_group,phone) values ('Seth',38,7,'M','AB',223344);```

-  In pandas we can do the same by adding the row at the end of the dataframe
   
![Screenshot from 2021-08-22 11-45-11.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629612949766/Q0rxIfhuz.png)
-  **Updating** a row in student_details table : <br>
    ```UPDATE student_details SET name = 'Seth Andrews' WHERE class=7 AND roll_no=38;```

- In pandas, we can update the value conditionally like this : 

![Screenshot from 2021-08-22 11-55-30.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629613583360/3kv-pbvpC.png)

### 10. Delete
- **Deleting** a  row in student_details table : <br>
   ```DELETE FROM student_details WHERE name = 'Seth Andrews' and class = 7;```

-  In pandas we can do the same with the help of **drop()** function :

![Screenshot from 2021-08-22 12-07-27.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629614273603/nbqwNQhb-.png)

### Conclusion
This is just introduction to how one can execute basic SQL operation using pandas and there are many more operations of SQL which can be easily done using pandas.
The datasets and python file I have used can be found here :  [Python Notebook](https://github.com/akash19x/Tutorials/blob/main/SQL%20operations%20in%20Pandas.ipynb) 
I'll be posting much more content of python and data science in my coming blogs.

Thanks for your time! :)
Checkout my youtube video on the same topic : https://www.youtube.com/watch?v=sUI00FYS0YA