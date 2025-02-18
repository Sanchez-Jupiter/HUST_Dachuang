### thoughts and notes

maximize the margin

data and label: $ (X_i, y_i) $

Hyperplane: $ W^TX + b = 0 $

3 steps: set model -> leave some parameters -> find those parameters using specific algorithm

Linear separable: $ y_i[W^TX + b] \ge 0$

#### Optimization problem:
minimize: $ \frac{1}{2}||W||^2 $

subject to $ y_i[W^TX + b] \ge 1$
(here "1" can be 2 ......)
#### traceback:

##### Fact 1:

$ W^TX + b = 0 $ and $ aW^TX + ab = 0 $ is the same hyperplane 

##### Fact2 :

the distance between $X_0$ and a hyperplane

$ d = \frac{|W^TX_0 + b|}{||W||} $ 

use a to zoom so that $ |W^TX_0 + b|  = 1$ 

then d become $ \frac{1}{||W||} $ 

Here $X_0$ is Support Vector, so for those who are not, $ |W^TX_0 + b|  \ge 1$ 

this is a convex problem
(The objective function is a quadratic term, and the constraint is a primary term)
Either no solution or only solution

Gradient descent

#### Non-Linear Separable

##### add Slack variable $\epsilon_i$

minimize: $ \frac{1}{2}||W||^2  + C\sum_{i = 1}^{N} \epsilon_i$

subject to $ y_i[W^TX + b] \ge 1 - \epsilon_i$

Regulation term $C\sum_{i = 1}^{N} \epsilon_i$

##### still find line, but in higher dimension

Reflection $\phi(X)$ from low to high dimension

minimize: $ \frac{1}{2}||W||^2  + C\sum_{i = 1}^{N} \epsilon_i$

subject to $ y_i[W^T\phi(X) + b] \ge 1 - \epsilon_i$

$P(Linear Separable) -> 1,  dimension -> +\infty$

here in SVM $\phi(X)$ is Infinite dimension,
We do not need to know the expression of $\phi(X)$, we only need to know the kernel function 

$K(X_1, X_2) = \phi(X_1)^T \phi(X_2)$

![alt text](<Sufficient and necessary condition of Kernel function.png>)

#### Prime problem
minimize $f(w)$

subject to 

$g_i(w)\le 0$

$h_i(w)=0$

#### Dual problem
maximize $\ \theta(\alpha, \beta) = inf_{all \ w}{L(w, \alpha, \beta)}$

$L(w, \alpha, \beta) = f(w) + \alpha^Tg(w) + \beta^Th(w)$

