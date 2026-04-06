![Amrita](https://github.com/user-attachments/assets/9c03a5d7-a5d2-4734-b7c6-2fc2c025f3b0)

# MFC 3 - 22MAT220
# ADMM-Based-Approach-for-Fund-of-Fund-Construction

## Team C - 15
### Team Members

| Name | Roll No |
|-----|-----|
| K. Sai Ganesh | CB.SC.U4AIE24226 |
| P. Sathvik | CB.SC.U4AIE24240 |
| Ch. Uday | CB.SC.U4AIE24210 |
| G. Varshini | CB.SC.U4AIE24216 |

### Abstract
The project goal is to find optimal allocation of assets in a fund of funds where the capital is spread across several mutual funds. To accomplish this goal, the Alternating Direction Method of Multipliers (ADMM) was used, which is a mathematical programming algorithm aimed at finding an optimal solution by maximizing or minimizing a function under various constraints such as expected return, covariance, transaction cost, and others. The initial condition assumes an equally weighted portfolio, and the algorithm iteratively finds an optimal allocation of funds. As can be seen from the findings, the developed algorithm efficiently solves the problem of optimal asset allocation in a fund of funds.

### Introduction

#### Problem Statement
A Fund of Funds (FOF) invests money across multiple mutual funds. The main problem is to decide how much to invest in each fund to get the best performance. Each fund has different return, risk, and transaction cost.
The goal is to:
- Maximize return
- Minimize risk
- Reduce costs
- Follow investment constraints

#### Motivation
The motivation behind this study is that there is need for an efficient means of optimal fund allocation. Unlike other simpler means, here we consider the ADMM optimization algorithm that is capable of dealing with even complicated constraints.
It will be useful in making better investment decisions while considering the risk involved.

### Outline 
This project aims to reduce the risk of losing money and maximizing the profits while investing in the stocks/ mutual funds. So we are going to discuss how to construct a better investment strategy using Fund of funds, which means investing money by splitting into many funds instead of stocks.The main goal is to find a balance between risk and return while taking into account real-world factors such as transaction costs. So we are trying to achieve this by using new optimization problem called ADMM. Here, the complex problem is broken to small and tiny problems into simpler ones. So this method is better and much faster than the traditional method like Mean-Variance model.

### Process flow
<img width="400" height="500" alt="image" src="https://github.com/user-attachments/assets/48dd7640-3973-42a8-a734-1da064d9095b" />


### Workflow  
1. Define portfolio optimization problem  
2. Split objective into separable components  
3. Apply ADMM updates  
4. Iterate until convergence  
5. Obtain optimal portfolio weights  

### Methodology
The Fund of Funds (FOF) optimization problem is formulated as a constrained optimization problem.
#### Objective function

$$
\min_{x \in \mathbb{R}^n}
\left(
\frac{1}{2} x^T P x + q^T x + \sum_{i=1}^{n} f_i(x_i)
\right)
$$

$$
\frac{1}{2} x^T P x
\quad \text{(represents the risk / variance of the portfolio)}
$$

$$
q^T x
\quad \text{(represents the expected return)}
$$

$$
\sum_{i=1}^{n} f_i(x_i)
\quad \text{(represents transaction cost)}
$$

**Subject to constraints:**

$$
\mathbf{1}^T x = 1 \quad \text{(Budget constraint)}
$$

$$
l_i \leq x_i \leq u_i,\; i = 1, \dots, n \quad \text{(Bound constraints)}
$$

$$
Ax \leq b \quad \text{(Linear constraint)}
$$

Budget constraints - All investment proportions must sum to 1 (100%).  
Bound Constraints - Each fund has minimum and maximum investment limits.  
Linear Constraint - Ensures portfolio follows rules like risk limits, diversification, category limits. 

#### Steps to solve
Transformation for ADMM
To apply ADMM, the problem is converted into a simpler form using variable splitting:
- Introduce auxiliary variable Z
- Convert constraints into equality form -> X = Z

New objective function becomes:

$$
\min_{x,z} \ \frac{1}{2} x^T P x + q^T x + \sum f_i(z_i)
$$

The optimization is solved iteratively using three updates:  
a) x - update  
 
$$
x^{k+1} = \arg\min \left( \frac{1}{2} x^T P x + q^T x + \frac{\rho}{2} \|x - z^k + u^k\|^2 \right)
$$

-> Solved using KKT system / linear equations

(b) z-update  

$$
z^{k+1} = \arg\min \left( \sum f_i(z_i) + \frac{\rho}{2} \|x^{k+1} - z + u^k\|^2 \right)
$$

-> Handled element-wise with projection and cost minimization

(c) u-update (dual variable)

$$
u^{k+1} = u^k + \left( x^{k+1} - z^{k+1} \right)
$$

Updates the penalty term to enforce consistency between x and z over iterations.

Stopping criteria  
Ensures the algorithm stops when both variables converge and the solution becomes stable.

### Dataset
In this project, a synthetic dataset is used to simulate real-world mutual fund data. The dataset contains information about multiple funds, where each fund categorized by:
- Expected Return -> Estimated profit from the fund
- Risk Value -> Represents volatility of the fund
- Fund Size -> Scale of the fund
- Transaction Parameters (a, b) -> Used in cost function
- Initial Allocation -> Equal distribution across all funds
### Notations
<img width="550" height="248" alt="image" src="https://github.com/user-attachments/assets/49b89f60-a9f7-404d-9d7e-92c991412efd" />


### Results
<img width="700" height="880" alt="image" src="https://github.com/user-attachments/assets/c7b35cd5-cdc2-431c-b8ed-202271b90e28" />

<img width="776" height="376" alt="image" src="https://github.com/user-attachments/assets/e698a4f3-dd44-4839-8593-1efd3476d7a1" />

#### Portfolio summary

| Metric              | Value         |
|--------------------|--------------|
| Total Investment   | ₹100,000     |
| Expected Return    | 0.18 (18%)   |
| Portfolio Risk     | 0.09         |

The optimized portfolio achieves a better balance between return and risk.

### Conclusion
This work attempted to solve the problem of optimal funds allocation within the Fund of Funds (FOF) structure through the use of the ADMM optimization algorithm. The model considered significant variables like return, risk, cost of transaction, and constraints in order to develop an effective optimization problem.

The solutions obtained show that with the help of the ADMM optimization approach, an improved optimal portfolio could be developed from the initial allocation while taking into account all constraints, thus providing better risk-reward balance. In addition, the model demonstrates efficient convergence, which allows us to apply it to large-size portfolios as well.

On the whole, this work proves that the use of the ADMM approach is an efficient tool for optimizing portfolio assets.

### Future work
-Extend to real-time stock data  
-Include more realistic constraints  
-Improve convergence speed  

### Acknowledgement
This project represents the successful application of the ADMM (Alternating Direction Method of Multipliers) algorithm in optimizing fund allocation. It integrates mathematical modeling, data analysis, and financial decision-making to achieve an effective balance between risk and return. The work demonstrates how optimization techniques like ADMM can be practically used in portfolio management to enhance investment efficiency and support data-driven financial planning.

### Additional information
Platform used:- Laptop / Matlab 2024b  
Hardware: CPU  
Matlab 2024b  
Time taken: 10.4015 seconds  
