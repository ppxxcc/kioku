# Exponential Curve Fit with Least Squares Method

## Derivation

We wish to find an exponential curve of the form

$$y = exp(bx)$$

which will intercept at $y=1$ and has a single parameter $b$, which will be found to maximize the accuracy of the curve fit.

We can perform a sum of least squares to find the best fit.

To make the operation linear, we will take the natural log on both sides.

$$log(y)=log\big(exp(bx)\big)$$

$$log(y)=log(bx)$$

In our least squares calculation, we wish to minimize the error between the real data point and the estimated curve.
The error can be expressed as:

$$log(y_i) - bx_i$$

where the term $log(y_i)$ corresponds to our real data, and $bx_i$ corresponds to our estimated point on the curve we fit.

For the least squares method, our total error will be the following. 

$$\sum_i{\big( log(y_i) - bx_i \big)^2}$$

This will be a sum of the errors for every point, squared.
The square comes from the fact that we don't desire positive and negative errors to cancel each other out.

We wish to find a certain $b$, where the total sum is minimal.

Recall that solving for where the derivative equals 0 will give the minima/maxima.

$$ \frac{\partial}{\partial b} \sum_i{\big( log(y_i) - bx_i \big)^2} = 0 $$

Now we simplify:

$$ \frac{\partial}{\partial b} \sum_i{ \big( log(y_i)-bx_i \big)  \big( log(y_i)-bx_i \big) } = 0 $$

$$ \frac{\partial}{\partial b} \sum_i{ \big( log^2(y_i) - 2log(y_i)bx_i + b^2x_i^2 \big) } = 0 $$

Take the partial derivative with respect to $b$:

$$ \sum_i{ \big( -2log(y_i)x_i + 2bx_i^2 \big) } = 0 $$

Simplify:

$$ 2 \sum_i{ \big( bx_i^2 - log(y_i)x_i \big) } = 0 $$

Since we wish to solve for b, let us split the summation and gather like terms. In addition, we can drop the factor of 2 by dividing both sides, given that the other side is equal to 0.

$$ 2 \Big( \sum_i{bx_i^2} - \sum_i{log(y_i)x_i} \Big) = 0 $$

$$ \sum_i{bx_i^2} - \sum_i{log(y_i)x_i} = 0 $$

$$ \sum_i{bx_i^2} = \sum_i{log(y_i)x_i} $$

Since $b$ is simply a constant, we can take it outside of the summmation:

$$ b \sum_i{x_i^2} = \sum_i{log(y_i)x_i} $$

Now, simply divide both sides to isolate and solve for b:

$$ b = \frac{\sum_i{x_i^2}}{\sum_i{log(y_i)x_i}}$$


## Conclusion

Provided a set of data points $(x_1, y_1), (x_1, y_1), ... , (x_n, y_n)$, we can find an exponential curve intercepting at $(0,1)$ with:

$$y=exp(bx)$$ 

where 

$$b = \frac{\sum_i{x_i^2}}{\sum_i{log(y_i)x_i}} $$
