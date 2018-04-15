### Gradient Descent  for Linear Regression
***
This example demonstrates how gradient descent solves the linear regression problem.


### Implementation
***
The code contains two class. The first class `gradient_descent` implements how gradient descent algorithm solves the linear regression problem. The second one `vis_gradient` visualizes the process of the gradient descent algorithm working.

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
Using `vis_gradient` to visualize training process.

 -  Visualize each training iteration error. 

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
vis.gradient_search() 
```

<img src = "\\animation\\gradient_search.gif" height = "400" width = "450">
