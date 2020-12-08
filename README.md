# Portfolio optimization with CVXPY

Do simple portfolio optimizations using:

 - [CVXPY](https://www.cvxpy.org) ([paper](https://arxiv.org/abs/1603.00943)), a modeling environment for [convex optimization](https://web.stanford.edu/~boyd/cvxbook/), supporting [many back-end solvers](https://www.cvxpy.org/tutorial/advanced/index.html#solve-method-options).
 - Data (mostly) from [Prof. Aswath Damodaran](http://pages.stern.nyu.edu/~adamodar/New_Home_Page/datacurrent.html) and [FRED](https://fred.stlouisfed.org/)

![Efficient Frontier](efrontier.png)

![Optimal portfolio transition map](transmap.png)

## Steps

1. Load asset return data from Damodaran website using `pd.read_excel`
2. Load gold and GDP data from FRED using `pandas_datareader` module
3. Manually fill in some missing data back to 1928.
4. Compute covariance matrix, long-only efficient frontier, and transition map using historical data (see above). Also compute 1972-present (post-gold standard) and 1983-present (post inflation-era).
5. Compute long-short efficient frontier and transition map, adding a random short asset with 5% annualized negative return and 90% correlation to S&P, and adding a 150% gross exposure constraint.
6. Compute efficient frontier using a factor model, using random set of returns for 1000 stocks and 10 random factor exposures and random factor covariances.

## Setup

You  *should* be able to [run directly in Google Colab](https://colab.research.google.com/github/druce/portfolio_optimization/blob/master/Portfolio%20optimization.ipynb#scrollTo=pgiV1eo3PWhx).

Or, to run locally

1. git clone this repo, cd to repo directory

2. Install [Anaconda](https://www.anaconda.com/products/individual)

3. Create virtual environment
```
conda create -n portfolio_opt
conda activate portfolio_opt
pip install -r requirements.txt
```

or
	
```
conda env create -f environment.yaml
conda activate portfolio_opt
```
4. `jupyter notebook`

5. Run `Portfolio optimization.ipynb`

