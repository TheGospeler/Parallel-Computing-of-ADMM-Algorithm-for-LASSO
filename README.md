## CMSE 822: Parallel Computing Final Project
First, give a brief description of your project topic idea and detail how you will address each of the specific project requirements given in this [here.](https://cmse822.github.io/projects) 

### Alternating Direction Method of Multilpliers (ADMM) Algortithm for LASSO.
#### Project Description:

The least absolute shrinkage and selection operator (lasso) method is a popular method in statistics and machine learning for regression analysis with regularization. However, the lasso problem is not an easy solve due to its $L_1$ lasso penalty, unlike the linear regression or ridge regression algortithm. But, algorithms such as the ADMM, have been developed to estimte the lasso estimator. 

$$\hat{x}^{\text{lasso}} = \arg\min_{x} \{ \frac{1}{2}\|Ax - b\|^2 + \lambda\|x\|_1 \}.$$

**The goal of this project is to parallelize the ADMM algorithm and reduce each iteration time, which will lead to convergence.**

#### Parallelization Strategies:
- Employ domain decomposition to split the LASSO problem into subproblems that can be solved independently in parallel.
- Utilizing a task-based approach where different stages of the ADMM algorithm (like variable updates) are treated as separate tasks.

#### Load Balancing and Memory Usage
- Implement dynamic load balancing to ensure even distribution of computational load as the number of tasks increases.
- Adaptively allocate resources based on the workload of each task (considering the iterative methods of ADMM).
- Analyze how memory usage scales with the number of tasks
- Optimize data structures and memory access patterns to minimize memory overhead and maximize efficiency, especially in a distributed computing environment

#### Verification Test
- This task have been performed using Python programming and will be used to verify the correctness of the parallel ADMM implementation.
- Based on this test suite, ensure that the LASSO solution remains consistent irrespective of the number of parallel tasks or the parallelization strategy used

#### Scaling Studies
- Measure thread-to-thread speedup and analyze how the solution scales with an increasing number of nodes and processors.
- Conduct weak and strong scaling studies to evaluate performance.
