# Coursera ML Andrew Ng

## Multivariate Linear Regression

### Multiple Features (Variables)
- theta-Transpose is a '1 x (n+1)' Matrix
- hypothesis representation: theta-Transpose . X

### GRadient Descent in multiple variables:
[Multivariate Gradient Descent](images/multiple_feature_gradient_descent.png)

### Feature Scaling
- make sure features are on similar scale
- so that the graph of the gradient descent isn't skewed and getting to the descent is quicker
- get every feature into approx -1 <= x(i) <= 1
- Mean Normalization: make features have approx zero mean
- x(i)-myu(i)/range/standard deviation, myu(i) is avverage.

### Learning Rate
- If learning rate (alpha) is too small: slow convergence
- If alpha is too large: J(theta) may not decrease on every iteration; may not converge
- for sufficiently small alpha, J(theta) should decrease on every iteration

### Features and Polynomial Regression
- frontage and depth -> Area
- sometimes changing the features to a new one is better

### Normal Equation
- Method to solve theta analytically
- We were solving for theta was a real number.
- What if theta is not a real number
- m examples, n features
- theta=(X'.X)^-1.X'.y
	- (X' X)^-1 
	- inverse of matrix X transpose . X
| Gradient Descent           | Normal Equation                            |
|----------------------------|--------------------------------------------|
| Need to choose alpha       | No need to choose alpha                    |
| Needs many iterations      | No need to iterate                         |
| O (kn^2)                   | O (n^3), need to calculate inverse of X'.X |
| Works well when n is large | Slow if n is very large                    |

### Notmal Equation Noninvertibility
- sigular / degenerate
- Octave: Pinv and inv
	- pinv = psuedo inv -> will give the value even when non-invertible
- non-invertible cause: 
  	- redundant features / linearly dependent: x1= size in feet; x2=size in m -> x1=3.28^2.x2
	- too many features: m<=n
