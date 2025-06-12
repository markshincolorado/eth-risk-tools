import pandas as pd
import numpy as np

def calc_volatility(price_series):
    returns = price_series.pct_change().dropna()
    return np.std(returns) * np.sqrt(252)

# Example use:
eth_prices = pd.Series([1800, 1850, 1780, 1900, 1950, 1890])
print("Annualized Volatility:", calc_volatility(eth_prices))
