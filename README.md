# ADMM-Based-Approach-for-Fund-of-Fund-Construction

## Team C - 15
### Team Members

| Name | Roll No |
|-----|-----|
| K. Sai Ganesh | CB.SC.U4AIE24226 |
| P. Sathvik | CB.SC.U4AIE24240 |
| Ch. Uday | CB.SC.U4AIE24210 |
| G. Varshini | CB.SC.U4AIE24216 |

### Outline 
This project aims to reduce the risk of losing money and maximizing the profits while investing in the stocks/ mutual funds. So we are going to discuss how to construct a better investment strategy using Fund of funds, which means investing money by splitting into many funds instead of stocks.The main goal is to find a balance between risk and return while taking into account real-world factors such as transaction costs. So we are trying to achieve this by using new optimization problem called ADMM. Here, the complex problem is broken to small and tiny problems into simpler ones. So this method is better and much faster than the traditional method like Mean-Variance model.

## Process flow
<img width="400" height="500" alt="image" src="https://github.com/user-attachments/assets/6134743e-cc80-4283-b2e5-bc397d5321be" />

### Workflow  
1. Define portfolio optimization problem  
2. Split objective into separable components  
3. Apply ADMM updates  
4. Iterate until convergence  
5. Obtain optimal portfolio weights  

## Objective function
### Optimization Problem

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

## Notations
<img width="550" height="248" alt="image" src="https://github.com/user-attachments/assets/997d06d7-1ac7-4ee5-bf60-7dd81426f903" />

### Results
<img width="700" height="880" alt="image" src="https://github.com/user-attachments/assets/83a0c7ad-24bf-4f09-9ce4-2b604509d68b" />

<img width="776" height="376" alt="image" src="https://github.com/user-attachments/assets/99a94b89-7606-4f73-9182-8f05b05261d9" />

### Conclusion
This project applies the ADMM (Alternating Direction Method of Multipliers) optimization technique to improve investment allocation across multiple funds. Starting from equal initial allocations, ADMM efficiently redistributes investments while satisfying category and risk constraints from the research paper. The optimized results show how ADMM can balance risk, return, and investment limits, making it a powerful approach for real-world portfolio optimization and fund management.

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
