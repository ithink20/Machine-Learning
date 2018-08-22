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

We can measure the accuracy of our [hypothesis](https://www.quora.com/What-is-hypothesis-in-machine-learning) function by using a cost function. This takes an average difference (actually a fancier version of an average) of all the results of the hypothesis with inputs from x's and the actual output y's.

![](http://latex.codecogs.com/gif.latex?J%28%5Ctheta_0%2C%20%5Ctheta_1%29%20%3D%20%5Cfrac%7B1%7D%7B2m%7D%20%5Csum_%7Bi%20%3D%201%7D%5E%7Bm%7D%20%28%5Chat%7By_i%7D%20-%20y_i%29%5E%7B2%7D%20%3D%20%5Cfrac%7B1%7D%7B2m%7D%20%5Csum_%7Bi%20%3D%201%7D%5E%7Bm%7D%20%28h_%5Ctheta%28x_i%29%20-%20y_i%29%5E%7B2%7D)

To break it apart, it is ![](http://latex.codecogs.com/gif.latex?%5Cfrac%7B1%7D%7B2%7D%5Cbar%7Bx%7D) where ![](http://latex.codecogs.com/gif.latex?%5Cbar%7Bx%7D) is the mean of the squares of ![](http://latex.codecogs.com/gif.latex?h_%5Ctheta%20%28x_%7Bi%7D%29%20-%20y_%7Bi%7D)

Following image summarizes it all:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/R2YF5Lj3EeajLxLfjQiSjg_110c901f58043f995a35b31431935290_Screen-Shot-2016-12-02-at-5.23.31-PM.png?expiry=1534723200000&hmac=ulOSb-5gvf4k5nFmcxPKgRMjr1oTyHhp2fCJjyQZ3Dw)


### Cost Function - Intution 1
Taking any color and going along the 'circle', one would expect to get the same value of the cost function. For example, the three green points found on the green line above have the same value for ![](http://latex.codecogs.com/gif.latex?J%28%5Ctheta_0%2C%20%5Ctheta_1%29) and as a result, they are found along the same line. The circled x displays the value of the cost function for the graph on the left when ![](http://latex.codecogs.com/gif.latex?%5Ctheta_0%20%3D%20800%20and%20%5Ctheta_1%20%3D%20-0.15) Taking another h(x) and plotting its contour plot, one gets the following graphs:
If we try to think of it in visual terms, our training data set is scattered on the x-y plane. We are trying to make a straight line (defined by ![](http://latex.codecogs.com/gif.latex?h_%5Ctheta%20%28x%29)) which passes through these scattered data points.

Our objective is to get the best possible line. The best possible line will be such so that the average squared vertical distances of the scattered points from the line will be the least. Ideally, the line should pass through all the points of our training data set. In such a case, the value of ![](http://latex.codecogs.com/gif.latex?J%28%5Ctheta_0%2C%20%5Ctheta_1%29) will be 0. The following example shows the ideal situation where we have a cost function of 0.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/_B8TJZtREea33w76dwnDIg_3e3d4433e32478f8df446d0b6da26c27_Screenshot-2016-10-26-00.57.56.png?expiry=1534723200000&hmac=pivC42NTy-ORt35jElhfs9f6l4eR7titjCa1XBFh2M8)

when ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3D%201), we get a slope of 1 which goes through every single data point in our model. Conversely, when ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3D%200.5), we see the vertical distance from our fit to the data points increase.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/8guexptSEeanbxIMvDC87g_3d86874dfd37b8e3c53c9f6cfa94676c_Screenshot-2016-10-26-01.03.07.png?expiry=1534723200000&hmac=aGcCZe-IE48CCqCti6UqcloxID_VwAGDchK7NUOi_yo)

This increases our cost function to 0.58. Plotting several other points yields to the following graph:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/fph0S5tTEeajtg5TyD0vYA_9b28bdfeb34b2d4914d0b64903735cf1_Screenshot-2016-10-26-01.09.05.png?expiry=1534723200000&hmac=gHs366iM3c_uT8UZpuq68UfWX8_TkY_Gj2ETryX4MnQ)

Thus as a goal, we should try to minimize the cost function. In this case, ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3D%201) is our global minimum.

### Cost Function - Intution 2

A contour plot is a graph that contains many contour lines. A contour line of a two variable function has a constant value at all points of the same line. An example of such a graph is the one to the right below.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/N2oKYp2wEeaVChLw2Vaaug_d4d1c5b1c90578b32a6672e3b7e4b3a4_Screenshot-2016-10-29-01.14.37.png?expiry=1534723200000&hmac=DnQcvwNEsMpLz2AiSU37nwu3YNmN5JfzVIOGanxKkmU)

Taking any color and going along the 'circle', one would expect to get the same value of the cost function. For example, the three green points found on the green line above have the same value for ![](http://latex.codecogs.com/gif.latex?J%28%5Ctheta_0%2C%5Ctheta_1%29) and as a result, they are found along the same line. The circled x displays the value of the cost function for the graph on the left when ![](http://latex.codecogs.com/gif.latex?%5Ctheta_0%20%3D%20800) and ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3D%20-0.15) Taking another h(x) and plotting its contour plot, one gets the following graphs:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/26RZhJ34EeaiZBL80Yza_A_0f38a99c8ceb8aa5b90a5f12136fdf43_Screenshot-2016-10-29-01.14.57.png?expiry=1534723200000&hmac=6wXeeCVfZf1FHzJFc2qkHfQ-9B3IBNrkkim4OKNnZLU)

When ![](http://latex.codecogs.com/gif.latex?%5Ctheta_0%20%3D%20360) and ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3D%200), the value of ![](http://latex.codecogs.com/gif.latex?J%28%5Ctheta_0%2C%20%5Ctheta_1%29)  in the contour plot gets closer to the center thus reducing the cost function error. Now giving our hypothesis function a slightly positive slope results in a better fit of the data.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/hsGgT536Eeai9RKvXdDYag_2a61803b5f4f86d4290b6e878befc44f_Screenshot-2016-10-29-09.59.41.png?expiry=1534723200000&hmac=XV5d0hizv2IUIH9T7cUe3oDwb0JUw6lXSGhobX0YvIk)

The graph above minimizes the cost function as much as possible and consequently, the result of ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1) and ![](http://latex.codecogs.com/gif.latex?%5Ctheta_0) tend to be around 0.12 and 250 respectively. Plotting those values on our graph to the right seems to put our point in the center of the inner most 'circle'.


## Gradient Descent

So we have our hypothesis function and we have a way of measuring how well it fits into the data. Now we need to estimate the parameters in the hypothesis function. That's where gradient descent comes in.

Imagine that we graph our hypothesis function based on its fields ![](http://latex.codecogs.com/gif.latex?%5Ctheta_0) and ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1) (actually we are graphing the cost function as a function of the parameter estimates). We are not graphing x and y itself, but the parameter range of our hypothesis function and the cost resulting from selecting a particular set of parameters.

We put ![](http://latex.codecogs.com/gif.latex?%5Ctheta_0) on the x-axis and ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1) on the y-axis, with the cost function on the vertical z axis. The points on our graph will be the result of the cost function using our hypothesis with those specific theta parameters. The graph below depicts such a setup.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/bn9SyaDIEeav5QpTGIv-Pg_0d06dca3d225f3de8b5a4a7e92254153_Screenshot-2016-11-01-23.48.26.png?expiry=1534723200000&hmac=Y6HxFQzu0ZYafsibMsmFXG1k6kVebqtEULojuUw3U3c)

We will know that we have succeeded when our cost function is at the very bottom of the pits in our graph, i.e. when its value is the minimum. The red arrows show the minimum points in the graph.

The way we do this is by taking the derivative (the tangential line to a function) of our cost function. The slope of the tangent is the derivative at that point and it will give us a direction to move towards. We make steps down the cost function in the direction with the steepest descent. The size of each step is determined by the parameter α, which is called the learning rate.

For example, the distance between each 'star' in the graph above represents a step determined by our parameter α. A smaller α would result in a smaller step and a larger α results in a larger step. The direction in which the step is taken is determined by the partial derivative of ![](http://latex.codecogs.com/gif.latex?J%28%5Ctheta_0%2C%5Ctheta_1%29). Depending on where one starts on the graph, one could end up at different points. The image above shows us two different starting points that end up in two different places.

The gradient descent algorithm is:

repeat until convergence:

![](http://latex.codecogs.com/gif.latex?%5Ctheta_j%20%3A%3D%20%5Ctheta_j%20-%20%5Calpha%20%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20%5Ctheta_j%7D%20J%28%5Ctheta_0%2C%20%5Ctheta_1%29)

where

j=0,1 represents the feature index number.

At each iteration j, one should simultaneously update the parameters ![](http://latex.codecogs.com/gif.latex?%5Ctheta_0%2C%20%5Ctheta_1%2C%20...%20%2C%20%5Ctheta_n)​	 . Updating a specific parameter prior to calculating another one on the ![](http://latex.codecogs.com/gif.latex?J%5E%7Bth%7D) iteration would yield to a wrong implementation.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/yr-D1aDMEeai9RKvXdDYag_627e5ab52d5ff941c0fcc741c2b162a0_Screenshot-2016-11-02-00.19.56.png?expiry=1534723200000&hmac=q2oVz5kdhfcfobxMPhh425ADReAKhFODWb3FxXiHzUU)


### Gradient Descent Intution

The formula for a single parameter was :

Repeat until convergence:

![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3A%3D%20%5Ctheta_1%20-%20%5Calpha%20%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20%5Ctheta_1%7D%20J%28%5Ctheta_1%29)

Regardless of the slope's sign for ![](http://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cmathrm%7Bd%7D%20%7D%7B%5Cmathrm%7Bd%7D%20%5Ctheta_1%7DJ%28%5Ctheta_1%29%2C%20%5Ctheta_1) eventually converges to its minimum value. The following graph shows that when the slope is negative, the value of ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1) increases and when it is positive, the value of ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1) decreases.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/SMSIxKGUEeav5QpTGIv-Pg_ad3404010579ac16068105cfdc8e950a_Screenshot-2016-11-03-00.05.06.png?expiry=1534723200000&hmac=ugf81PGrdc0_sbXkrecz3FOy6MgTK5JWGHXylxhrp4k)

On a side note, we should adjust our parameter ![](http://latex.codecogs.com/gif.latex?%5Calpha%u03B1) to ensure that the gradient descent algorithm converges in a reasonable time. Failure to converge or too much time to obtain the minimum value imply that our step size is wrong.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/UJpiD6GWEeai9RKvXdDYag_3c3ad6625a2a4ec8456f421a2f4daf2e_Screenshot-2016-11-03-00.05.27.png?expiry=1534723200000&hmac=BM6MlrWlqfnDg9Xf070Vti0SJP-6bXzPIkxEYdr8nqo)

How does gradient descent converge with a fixed step size ![](http://latex.codecogs.com/gif.latex?%5Calpha%u03B1)?

The intuition behind the convergence is that ![](http://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cmathrm%7Bd%7D%20%7D%7B%5Cmathrm%7Bd%7D%20%5Ctheta_1%7DJ%28%5Ctheta_1%29) approaches 0 as we approach the bottom of our convex function. At the minimum, the derivative will always be 0 and thus we get:


![](http://latex.codecogs.com/gif.latex?%5Ctheta_1%20%3A%3D%20%5Ctheta_1%20-%20%5Calpha%20*%200)



![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/RDcJ-KGXEeaVChLw2Vaaug_cb782d34d272321e88f202940c36afe9_Screenshot-2016-11-03-00.06.00.png?expiry=1534723200000&hmac=BfvD6Q9eYuc2UTqkD0tbrxY8LpBTfSieaRB1du9KihA)



## Gradient Descent For Linear Regression


When specifically applied to the case of linear regression, a new form of the gradient descent equation can be derived. We can substitute our actual cost function and our actual hypothesis function and modify the equation to :


![](http://latex.codecogs.com/gif.latex?%5Cbegin%7Balign*%7D%20%5Ctext%7Brepeat%20until%20convergence%3A%20%7D%20%5Clbrace%20%26%20%5Cnewline%20%5Ctheta_0%20%3A%3D%20%26%20%5Ctheta_0%20-%20%5Calpha%20%5Cfrac%7B1%7D%7Bm%7D%20%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bm%7D%28h_%5Ctheta%28x_%7Bi%7D%29%20-%20y_%7Bi%7D%29%20%5Cnewline%20%5Ctheta_1%20%3A%3D%20%26%20%5Ctheta_1%20-%20%5Calpha%20%5Cfrac%7B1%7D%7Bm%7D%20%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bm%7D%5Cleft%28%28h_%5Ctheta%28x_%7Bi%7D%29%20-%20y_%7Bi%7D%29%20x_%7Bi%7D%5Cright%29%20%5Cnewline%20%5Crbrace%26%20%5Cend%7Balign*%7D)

where m is the size of the training set, ![](http://latex.codecogs.com/gif.latex?%5Ctheta_0) a constant that will be changing simultaneously with ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1) and ![](http://latex.codecogs.com/gif.latex?x_i%2C%20y_i) are values of the given training set (data).

Note that we have separated out the two cases for ![](http://latex.codecogs.com/gif.latex?%5Ctheta_j) into separate equations for ![](http://latex.codecogs.com/gif.latex?%5Ctheta_0) and ![](http://latex.codecogs.com/gif.latex?%5Ctheta_1); and that for
![](http://latex.codecogs.com/gif.latex?%5Ctheta_1) we are multiplying ![](http://latex.codecogs.com/gif.latex?x_i) at the end due to the derivative. The following is a derivation of ![](http://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%20%7D%7B%5Cpartial%20%5Ctheta_j%7DJ%28%5Ctheta%29) for a single example :

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/QFpooaaaEea7TQ6MHcgMPA_cc3c276df7991b1072b2afb142a78da1_Screenshot-2016-11-09-08.30.54.png?expiry=1534723200000&hmac=Lfc92AaAowB6Sqb5a7T2ilLczWZY-KA8iylhNv2__S4)

The point of all this is that if we start with a guess for our hypothesis and then repeatedly apply these gradient descent equations, our hypothesis will become more and more accurate.

So, this is simply gradient descent on the original cost function J. This method looks at every example in the entire training set on every step, and is called batch gradient descent. Note that, while gradient descent can be susceptible to local minima in general, the optimization problem we have posed here for linear regression has only one global, and no other local, optima; thus gradient descent always converges (assuming the learning rate α is not too large) to the global minimum. Indeed, J is a convex quadratic function. Here is an example of gradient descent as it is run to minimize a quadratic function.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/xAQBlqaaEeawbAp5ByfpEg_24e9420f16fdd758ccb7097788f879e7_Screenshot-2016-11-09-08.36.49.png?expiry=1534723200000&hmac=JoIMmYgQ8-Q1OYTh7S3VJgjqjb93W8TaI_lNhJH2SLk)

The ellipses shown above are the contours of a quadratic function. Also shown is the trajectory taken by gradient descent, which was initialized at (48,30). The x’s in the figure (joined by straight lines) mark the successive values of θ that gradient descent went through as it converged to its minimum.
