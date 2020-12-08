# Portfolio optimization with CVXPY

Do simple portfolio optimizations using:

 - [CVXPY](https://www.cvxpy.org) ([paper](https://arxiv.org/abs/1603.00943)) is a modeling environment for [convex optimization](https://web.stanford.edu/~boyd/cvxbook/), supporting [many back-end solvers](https://www.cvxpy.org/tutorial/advanced/index.html#solve-method-options).
 - Data used are historical returns from [Prof. Aswath Damodaran](http://pages.stern.nyu.edu/~adamodar/New_Home_Page/datacurrent.html) and [FRED](https://fred.stlouisfed.org/)

![Efficient Frontier](efrontier.png)

![Optimal portfolio transition map](transmap.png)

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

