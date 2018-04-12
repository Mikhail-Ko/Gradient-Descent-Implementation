<<<<<<< HEAD
### Gradient Descent Implementation for Linear Regression
***
This example demonstrates how gradient descent slove linear regression problem.

### Gradient Descent Algorithm
***
Before we run gradient descent algorithm, we need to design the hypothesis and [loss function](https://en.wikipedia.org/wiki/Loss_function).
 - Hypothesis : $\ y\ = b\ +\ wx\ \ $ ( b and w denote bias and slope)
 - Loss Function :$\ \frac{1}{2N}\sum\limits_{i=1}^{N}(\hat{y}_i\ -\ (b\ +\ wx_i))^2$
 
We hope our hypothesis can fit the set of points better, so the loss must be smaller.
Therefore, it can consider as an optimization problem.

 - optimization : $ \theta^*\ =\ arg\min_{\theta}^{}L(\theta)\ \ \ $ (L : Loss Function, $\theta$ : parameter)
 
Formulation : 
 1. $\frac{\partial L}{\partial W}\ =\ \frac{1}{N}\sum\limits_{i=1}^{N}(\hat{y}_i-(b\ +\ wx_i))(-x_i)$
 2. $\frac{\partial L}{\partial b}\ =\ \frac{1}{N}\sum\limits_{i=1}^{N}(\hat{y}_i-(b\ +\ wx_i))(-1)$

Update Parameter (n denote number of iteration):
 - Repeat : $\left\{\begin{aligned}w^n\ =\ w^{n-1}\ -\ \tau\frac{\partial L}{\partial W} \\ b^{n}\ =\ b^{n-1}\ -\ \tau\frac{\partial L}{\partial W}\end{aligned}\right.$

### Implementation
***
The code contains two class. One of the class the name called `gradient_descent` implement how gradient descent algorithm slove linear regression problem. The other one class called `vis_gradient` visualize the process of the gradient descent algorithm working.

```python

df = np.genfromtxt(fname = "data.csv", delimiter = ',') # read data 
y, x = df[:, 0], df[:, 1]

num_iter = 1000  # set number of iteration
learning_rate = 10**(-5) # set learning rate

gd = gradient_descent(num_iteration = num_iter, learning_rate = learning_rate)
parameter, err = gd.calculate_gradient(y, x, rand_seed = 123) # get each training iteration parameter and error 

bias = parameter[:, 0]
slope = parameter[:, 1]
```
### Visualization
***
Using `vis_gradient` class to visualize training process.

 -  Visualize each training iteration error 

```python

vis = vis_gradient(x = x, y = y, bias = bias, slope = slope, error = err, num_iter = num_iter)

vis.iteration_error() 
```

<img src = "\\animation\\gradient_error.gif" height = "400" width = "480" >

 -  Visualize fitting process.

```python
vis.fit_process() 
```

<img src = "\\animation\\fit_process.gif" height = "400" width = "450" >

 -  Visualize gradient search.

```python
vis.gradent_search() 
```

<img src = "\\animation\\gradient_search.gif" height = "400" width = "450">
=======
## Gradient Descent Implementation for Linear Regression
---
This example demonstrates how gradient descent slove linear regression problem.
>>>>>>> adf63b842c9ddca690cfe08f53bdbb138148f25f
