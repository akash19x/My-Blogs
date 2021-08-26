## Handling categorical data in python for machine learning.

In machine learning, our models generally require input features and target output to be numeric.
But at times, our dataset contains categorical values which needs to be pre-processed before feeding it into the model.

**What actually is Categorical data?**

• Categorical data is the data which contains only a limited number of possible values.

• Example : Consider a survey which tells which brand of phones people use and options can be : Apple, Samsung or Vivo.
Here, the data is categorical and we must chose one from these.

**Types of categorical variables :**

1- Nominal Variables : It is the categorical variable where there is no relationship between the values.

Example : A colour variable with values - red, blue, black.

There is no relationship between the colours.

2- Ordinal Variable : Categorical variable where there is relationship between values and there is a ranked ordering.
Eg : The variable income can have values like - low, moderate and high.

There is a relationship : 
low < moderate < high

### How to actually handle categorical data?

1- Ordinal Encoding.

2- One Hot Encoding.

**Ordinal Encoding**

• It involves mapping each unique label to an integer value. 

• This is mainly used when there is a relationship between the categories.

• Example: Income column, low becomes 0, moderate becomes 1 and high becomes 2.

![E9jtx24VUAcKWnR.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1629993882346/ySB1eyT-E.png)

**Code :**

![ord.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1629993927420/QfBrnLNEs.jpeg)

**One Hot Encoding : **

• In One Hot Encoding, we convert each categorical value into a new column and assign a binary value of 0 or 1 into those columns.

• It is more efficient than ordinal encoder in many problems and it prepares the data to get better predictions.

Example : 

![o.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1629993987438/qAbKRf9hl.jpeg)

**Code : **

![ohecode.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1629994024358/nTxS1Dsmt.jpeg)

Thanks for reading folks.

There are many other ways too like Dummy Variables etc n I'll write a blog on it soon for much more details.

Will keep on sharing these small blogs on various python and data science topics.

Thanks! :)