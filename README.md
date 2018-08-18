# Machine-Learning :bulb:

### Supervised Learning
In Supervised Learning, we are given a dataset and already know what our correct output should look like, having the idea that there is relationship between input and output.

Supervised learning problems are chategorized into "regression" and "classification" problems. In a regression problem, we are trying to predict the results within the continuous output, meaning that we are trying to map input variables to some continuous function. **Ex: House Price Predicition**.

In a classification problem, we are instead trying to predict results in a discrete output. In other words, we are trying to map input variables into discrete categories.**Ex: Breast Cancer**

**Example 1:**

Given data about the size of houses on the real estate market, try to predict their price. Price as a function of size is a continuous output, so this is a regression problem.

We could turn this example into a classification problem by instead making our output about whether the house "sells for more or less than the asking price." Here we are classifying the houses based on price into two discrete categories.

**Example 2:**

(a) Regression - Given a picture of a person, we have to predict their age on the basis of the given picture

(b) Classification - Given a patient with a tumor, we have to predict whether the tumor is malignant or benign.


### Unsupervised Learning

Unsupervised learning allows us to approach problems with little or no idea what our results should look like. We can derive structure from data where we don't necessarily know the effect of the variables.

We can derive this structure by clustering the data based on relationships among the variables in the data.

With unsupervised learning there is no feedback based on the prediction results.

**Example:**

Clustering: Take a collection of 1,000,000 different genes, and find a way to automatically group these genes into groups that are somehow similar or related by different variables, such as lifespan, location, roles, and so on.

Non-clustering: The "Cocktail Party Algorithm", allows you to find structure in a chaotic environment. (i.e. identifying individual voices and music from a mesh of sounds at a (cocktail party).


### Cost Function

We can measure the accuracy of our hypothesis function by using a cost function. This takes an average difference (actually a fancier version of an average) of all the results of the hypothesis with inputs from x's and the actual output y's.

![](http://latex.codecogs.com/gif.latex?J%28%5Ctheta_0%2C%20%5Ctheta_1%29%20%3D%20%5Cfrac%7B1%7D%7B2m%7D%20%5Csum_%7Bi%20%3D%201%7D%5E%7Bm%7D%20%28%5Chat%7By_i%7D%20-%20y_i%29%5E%7B2%7D%20%3D%20%5Cfrac%7B1%7D%7B2m%7D%20%5Csum_%7Bi%20%3D%201%7D%5E%7Bm%7D%20%28h_%5Ctheta%28x_i%29%20-%20y_i%29%5E%7B2%7D)

To break it apart, it is ![](http://latex.codecogs.com/gif.latex?%5Cfrac%7B1%7D%7B2%7D%5Cbar%7Bx%7D) where ![](http://latex.codecogs.com/gif.latex?%5Cbar%7Bx%7D) is the mean of the squares of ![](http://latex.codecogs.com/gif.latex?h_%5Ctheta%20%28x_%7Bi%7D%29%20-%20y_%7Bi%7D)

Following image summarizes it all:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/R2YF5Lj3EeajLxLfjQiSjg_110c901f58043f995a35b31431935290_Screen-Shot-2016-12-02-at-5.23.31-PM.png?expiry=1534723200000&hmac=ulOSb-5gvf4k5nFmcxPKgRMjr1oTyHhp2fCJjyQZ3Dw)


### Cost Function - Intution 1

If we try to think of it in visual terms, our training data set is scattered on the x-y plane. We are trying to make a straight line (defined by ![](http://latex.codecogs.com/gif.latex?h_%5Ctheta%20%28x%29)) which passes through these scattered data points.

Our objective is to get the best possible line. The best possible line will be such so that the average squared vertical distances of the scattered points from the line will be the least. Ideally, the line should pass through all the points of our training data set. In such a case, the value of ![](http://latex.codecogs.com/gif.latex?J%28%5Ctheta_0%2C%20%5Ctheta_1%29) will be 0. The following example shows the ideal situation where we have a cost function of 0.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/_B8TJZtREea33w76dwnDIg_3e3d4433e32478f8df446d0b6da26c27_Screenshot-2016-10-26-00.57.56.png?expiry=1534723200000&hmac=pivC42NTy-ORt35jElhfs9f6l4eR7titjCa1XBFh2M8)

when ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3D%201), we get a slope of 1 which goes through every single data point in our model. Conversely, when ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3D%200.5), we see the vertical distance from our fit to the data points increase.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/8guexptSEeanbxIMvDC87g_3d86874dfd37b8e3c53c9f6cfa94676c_Screenshot-2016-10-26-01.03.07.png?expiry=1534723200000&hmac=aGcCZe-IE48CCqCti6UqcloxID_VwAGDchK7NUOi_yo)

This increases our cost function to 0.58. Plotting several other points yields to the following graph:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/fph0S5tTEeajtg5TyD0vYA_9b28bdfeb34b2d4914d0b64903735cf1_Screenshot-2016-10-26-01.09.05.png?expiry=1534723200000&hmac=gHs366iM3c_uT8UZpuq68UfWX8_TkY_Gj2ETryX4MnQ)

Thus as a goal, we should try to minimize the cost function. In this case, ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3D%201) is our global minimum.


