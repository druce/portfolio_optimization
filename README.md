# Portfolio optimization with CVXPY

Do a few classic portfolio optimizations using:

 - [CVXPY](https://www.cvxpy.org) ([paper](https://arxiv.org/abs/1603.00943)), a modeling environment for [convex optimization](https://web.stanford.edu/~boyd/cvxbook/), supporting [many back-end solvers](https://www.cvxpy.org/tutorial/advanced/index.html#solve-method-options).
 - Data (mostly) from [Prof. Aswath Damodaran](http://pages.stern.nyu.edu/~adamodar/New_Home_Page/datacurrent.html) and [FRED](https://fred.stlouisfed.org/)

![Efficient Frontier](efrontier.png)

![Optimal portfolio transition map](transmap.png)

## Online data

- [Aswath Damodaran](https://pages.stern.nyu.edu/~adamodar/). See the [FAQ tab in his XLS](https://www.stern.nyu.edu/~adamodar/pc/datasets/histretSP.xls) for details on individual asset returns.
- [FRED](https://fred.stlouisfed.org/)
- [Shiller data](http://www.econ.yale.edu/~shiller/data.htm)
- [Ken French](https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html)
- [Macrotrends](https://www.macrotrends.net/)

Currently use Damodaran data for returns.

## Steps

1. Load asset return data from Damodaran website using `pd.read_excel`.
2. Load GDP data from FRED using `pandas_datareader` module.
3. Manually fill in some missing data back to 1928.
4. Compute covariance matrix, long-only efficient frontier, and transition map using historical data (see above). Also compute same outputs for 1972-present (post-gold standard) and 1983-present (post-inflation era).
5. Compute long-short efficient frontier and transition map, adding a random short asset with 5% annualized negative return and 90% correlation to S&P, and adding a 150% gross exposure constraint.
6. Compute some allocations using hierarchical risk parity model for comparison.
6. Compute an efficient frontier using a factor model, using a random set of returns for 1000 stocks and 10 random factor exposures and a random factor covariance matrix.


This mostly follows the [cvxpy tutorial](https://colab.research.google.com/github/cvxgrp/cvx_short_course/blob/master/applications/portfolio_optimization.ipynb) but uses real historical data, and visualizes the full efficient frontier and transition map.

#### Takeaways 

 - Gold adds some value for most portfolios, except in most disinflationary environment at higher risk tolerances. 
 - TIPS should be a more direct inflation hedge with a US government guaranteed real return but we don't have data back very far.
 - If you can find good shorts and use leverage, you can supercharge returns.
 
## Setup

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

## Further reading

 - [CVXPY tutorial](https://www.cvxpy.org/version/1.1/tutorial/index.html)
 - [Convex optimization short course](https://stanford.edu/~boyd/papers/cvx_short_course.html)
