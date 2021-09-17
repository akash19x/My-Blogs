## Time Series Analysis with Python (Part 1)

Time series analysis basically is a way of studying a sequence of data points collected over a period of time. In this, the data is recorded from time to time consistently and then analysed further to study the various trends in data with time. 

### Examples of Time Series Analysis

- **Stock Market** : Time Series analysis is used in stock markets where the prices of various stocks move up and down from time to time and analysts record these prices at different instances of time and then do time series analysis to determine various trends in stock prices.

- **Sales Report** : Companies analyse their sales (annually or semi annually) just to have an idea of how they are performing over time. The sales data is recorded at various instances of time and helps these organisations to study the various trends and perform some actions after analysing these time series sales data.

- **Weather Forecasting** : The Meteorological Department weather by looking at historical trends of whether data which were recorded over a period of time.

### Working with Time Series in Python
 
**Pandas** library in python have a range of tools for working with dates, times and dime indexed data. There are different types of date and time data like :

- ***Time stamp*** : It references to specific moments in time. Like September 17, 2021 at 6:30 A.M
 
-  ***Time period*** : It references to length of time between a specific begin point and end point. <br>Eg: The year 2019

- ***Time delta*** :  It specifies the exact length of time. Ex : 67.88 seconds

## Coding

### Native Python dates and times

Python has built-in date and time modules : **datetime** and **dateutil** and we can manually perform some functionalities like :

- Building a date using datetime type : <br> 
![Screenshot from 2021-09-17 18-27-43.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631883494812/z18HwDtxe.png)

- We can also parse dates from a variety of string formats using dateutil like : <br>
![Screenshot from 2021-09-17 18-29-30.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631883588489/KIahlF7D6.png)

- Once we have datetime object, we can even print the day of the week : <br>
![Screenshot from 2021-09-17 18-31-54.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631883729983/rQpFxwjfk.png)

### Numpy's datetime64

Numpy's datetime64 type gives much more functionalities than native datetime modules. It encodes dates as 64-bit integers and allow array of dates to be represented very compactly.

- datetime64 can be created by using numpy :<br>
![Screenshot from 2021-09-17 18-37-56.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631884090384/FiiIRgHcm.png)

- Once we have the date, we can do various operations on it like, adding next 10 dates in an array : <br>
![Screenshot from 2021-09-17 18-40-13.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631884228529/D8MM66RuN.png)

**np.arrange** function basically returns evenly spaced values within a given interval.

### Dates and Times in Pandas (Intro)

Pandas offers even more functionalities over numpy as it is built on numpy. It combines datetime and dateutil with much **efficient storage** and vectorized interface of numpy's datetime64. 

- We can parse flexibly formatted string dates and use format codes to output the day of the week as shown above : <br>
![Screenshot from 2021-09-17 18-47-15.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631884651054/dvkCxjrQ9.png)

- We can do numpy style vectorized operations directly on the same object :<br>
![Screenshot from 2021-09-17 18-49-34.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631884788506/G-CI1CwPR.png)

### Pandas indexing with time

We can index our data by timestamps. Ex : We can actually create a series which has time indexed data. <br>
![Screenshot from 2021-09-17 18-54-12.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631885069587/QE9nIgxu0.png)

Now that this data is in series, we can perform any Series indexing patterns. Let's select only a range of index now.

![Screenshot from 2021-09-17 18-56-13.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631885183336/3KkxS4VlH.png)

There is also a **special indexing operation** such as passing the year to obtain a slice of that data as shown below.<br>
![Screenshot from 2021-09-17 18-57-45.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631885281617/RtVrta1AR.png)

### pd.date_range()
It is a very useful function which returns the datetime index of a fixed frequency.

- By default, the frequency is  1 day <br>
![Screenshot from 2021-09-17 19-02-23.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631885557781/erKi9f3b-.png)

- We can find business days which excludes weekends by giving freq = 'B' <br>
![Screenshot from 2021-09-17 19-05-17.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1631885729529/Wk0eScAoF.png)

We can perform much more pandas date time operations just by playing around with datatypes and variables.  

### Conclusion

This was part 1 of the **Time Series Analysis with Python** where we have seen what is time series, where do we use it and an introduction to how time and date variables work in python.

In the next blog (Part-2), we shall see how we can visualise these time series data using different types of plots and graphs.

So, stay tuned and thanks for your read! :)

Do give me a follow if you like it as I post Python, Machine Learning and Data Science related stuffs on this blog frequently.












