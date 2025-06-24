# Portfolio-Optimization-with-Python-using-Efficient-Frontier
1. What is Portfolio Optimization?
   - The process of choosing asset weights to maximize return for a given risk or minimize risk for a given return.

2. Getting Stock Data:
   - Download historical Adjusted Close prices for selected stocks.
   - Adjusted Close accounts for dividends and splits, useful for return calculations.

3. Calculate Log Returns:
   - Log returns = ln(P_t / P_(t-1)), used because they are additive over time.
   - Additivity simplifies return calculations over multiple periods.

4. Covariance Matrix:
   - Shows how pairs of stocks move together.
   - Positive covariance means they move in the same direction.
   - Negative covariance means they move inversely.
   - Used to calculate portfolio risk considering asset correlations.

5. Expected Annual Returns:
   - Calculate yearly returns by resampling prices annually.
   - Expected return = mean of yearly returns for each asset.
   - Represents the average annual gain or loss for each stock.

6. Annualized Volatility:
   - Volatility = standard deviation of daily log returns scaled by sqrt(250) (trading days).
   - Measures risk or variability of returns.
   - Higher volatility means higher investment risk.

7. Individual Asset Summary:
   - Combine expected returns and volatility for each stock to assess risk-return tradeoff.

8. Monte Carlo Simulation:
   - Generate many portfolios by randomly assigning weights to assets.
   - For each portfolio, calculate weighted return and risk (volatility).
   - Helps explore possible combinations to find efficient portfolios.

9. Portfolio DataFrame:
   - Store portfolio returns, volatility, and weights for analysis and plotting.

10. Plot the Efficient Frontier:
    - Scatter plot of portfolio risk vs return.
    - The frontier is the boundary of optimal portfolios offering best return per risk level.
    - Points inside the frontier are sub-optimal.

11. Minimum Volatility Portfolio:
    - The portfolio with the lowest risk.
    - Suitable for risk-averse investors.

12. Sharpe Ratio and Optimal Risky Portfolio:
    - Sharpe Ratio = (Portfolio Return - Risk-Free Rate) / Portfolio Volatility.
    - Measures risk-adjusted return.
    - Portfolio with highest Sharpe Ratio offers best tradeoff between risk and return.

13. Summary:
    - Portfolio optimization balances risk and return.
    - Diversification reduces risk via assets with low or negative correlations.
    - Efficient Frontier helps visualize optimal trade-offs.
    - Sharpe Ratio identifies portfolios with best risk-adjusted returns.
