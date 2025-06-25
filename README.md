# Portfolio-Optimization-with-Python-using-Efficient-Frontier

"""
Portfolio Optimization Explanation with Formulas:

1. What is Portfolio Optimization?
   - Process of choosing asset weights (w_i) to maximize return or minimize risk.
   - Goal: maximize expected return E[R_p] for a given portfolio risk σ_p, or minimize σ_p for a target return.

2. Getting Stock Data:
   - Historical Adjusted Close prices for assets (stocks) are used.
   - Adjusted Close accounts for dividends and stock splits.

3. Calculate Log Returns:
   - Log return at time t:
     r_t = ln(P_t / P_(t-1))
   - Log returns are additive over time:
     ln(P_t / P_0) = ∑_{k=1}^{t} r_k

4. Covariance Matrix:
   - Covariance between assets i and j measures how returns move together:
     Cov(R_i, R_j) = E[(R_i - μ_i)(R_j - μ_j)]
   - Covariance matrix Σ contains all covariances for asset pairs.
   - Positive covariance → move together; negative → move oppositely.

5. Expected Annual Returns:
   - Annual expected return for asset i:
     E[R_i] = mean of yearly returns
   - Yearly returns computed by:
     R_{year} = (P_{end_of_year} - P_{start_of_year}) / P_{start_of_year}

6. Annualized Volatility:
   - Volatility (standard deviation) of asset i's daily log returns:
     σ_{daily} = std_dev(r_t)
   - Annual volatility:
     σ_{annual} = σ_{daily} * sqrt(250)
   - Where 250 = approximate trading days per year.

7. Individual Asset Summary:
   - Table of (E[R_i], σ_i) per asset for risk-return view.

8. Monte Carlo Simulation:
   - Randomly generate portfolio weights w = [w_1, w_2, ..., w_n], with ∑ w_i = 1
   - Portfolio expected return:
     E[R_p] = ∑_{i=1}^n w_i E[R_i] = wᵀ * E[R]
   - Portfolio variance:
     σ_p^2 = wᵀ * Σ * w = ∑_{i=1}^n ∑_{j=1}^n w_i w_j Cov(R_i, R_j)
   - Portfolio volatility:
     σ_p = sqrt(σ_p^2)
   - Generate many portfolios to find optimal risk-return combinations.

9. Portfolio DataFrame:
   - Stores returns, volatility, and weights for each portfolio.

10. Plot the Efficient Frontier:
    - Graph of σ_p (volatility, x-axis) vs E[R_p] (return, y-axis).
    - Frontier shows portfolios with maximum return for given risk or minimum risk for given return.

11. Minimum Volatility Portfolio:
    - Portfolio with lowest risk σ_p:
      min(σ_p) subject to ∑ w_i = 1

12. Sharpe Ratio and Optimal Risky Portfolio:
    - Sharpe Ratio:
      S = (E[R_p] - R_f) / σ_p
    - R_f = risk-free rate (e.g., government bond yield)
    - Optimal risky portfolio maximizes Sharpe ratio:
      max_w S(w)

13. Summary:
    - Portfolio optimization balances maximizing returns and minimizing risk.
    - Diversification reduces portfolio risk by combining assets with low or negative correlations.
    - Efficient frontier visualizes best risk-return trade-offs.
    - Sharpe ratio identifies portfolios with best risk-adjusted returns.
