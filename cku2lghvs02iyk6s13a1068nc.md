## How to find the best model and parameters in Machine Learning easily?

While learning machine learning in the initial stages, I often used to ask myself questions like :

- I know different types of learning models but is there a way to validate these models which one is better?

- Can I find the best machine learning model and the best parameter in one go without any extra writing code and evaluating results?

The answer to those questions could have saved a lot of my efforts.

What I used to do before was using the model validation techniques like :

- **train_test_split** : It splits the data into one training set and one testing set and model's accuracy is measured by evaluating it on testing data.

- **cross validation** : It is more accurate but slower than train_test_split because here the data is divided into multiple folds and training test and testing set are different in different iterations and the average accuracy gives us the accuracy of a model

But the problem with these techniques was :

Let's say I have model_A and model_B and If I had to find which is better, I just trained my model using each of them, found the best accuracy and picked the one with better score. But what is the number of models out of which I have to find the best one is 20? That means I had to train my model 20 times (which consumes lots of time, energy and monitoring) and it becomes a tedious job. 😭

Then one day, I was really tired with this and decided to search a better and efficient way to find the best model and parameter in one go and I came across the concepts like **GridSearchCV** and that made my life much easier. 😄 I'm still so happy that I came across this concept and a little sad why I didn't do this research earlier.

### Grid Search CV 😎

The Grid Search Cross Validation is a technique used for estimating test-set performance of a model. Grid-search is a way to select the best of a family of models, parametrised by a grid of parameters.
It basically means, we need to give the names of the models and parameters and it will give us the best model and it's parameter.

**Let's see how can we implement it in Python : **

#### Step 1 

Import the GridSearchCV and all the models which we want to validate.

![carbon (9).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632742834701/wPNZfMBzf.png)

#### Step 2

Create a model grid, that is a dictionary which contains all the models and their parameters and out of which we have to find the best one in one go!

![carbon (10).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632742963542/f-OIgwNrs.png)

#### Step 3

Iterate the grid using for loop and append the result of each model to a variable **scores**.

![carbon (11).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632743093958/cCWHDHA3_.png)

#### Step 4 
Create a dataframe out of the variable scores which contains a dictionary.

![carbon (12).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632743191774/kP9NGIAbi.png)

#### Step 5
See the results and chose the best set of models and parameters! 😇

![Screenshot from 2021-09-27 17-17-29.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632743270619/6A8W7RRPg.png)

Here, we can see that Support Vector Machine learning model with C=1 and kernel = rbf is the best possible model for this dataset and we shall go with it.

### Conclusion

With these simple steps we can find the best model and parameters in Machine Learning very easily.
Special thanks to **codebasics** channel on youtube where I found this concept for the very first time and it is helping me alot to solve such problems.

I hope it helps you too! Thanks for reading. 😇







