# portfolio_optimization
## Portfolio optimization with cvxpy

![Optimal portfolio transition map](transmap.png)

![Efficient Frontier](efrontier.png)

[Portfolio\ optimization.ipynb](Portfolio\ optimization.ipynb)

Do simple portfolio optimizations using historical returns from Aswath Damadoran's data and FRED

 - https://www.cvxpy.org
 - http://pages.stern.nyu.edu/~adamodar/New_Home_Page/datacurrent.html
 - https://fred.stlouisfed.org/
 - https://web.stanford.edu/~boyd/cvxbook/

### Environment setup
1. git clone this repo, cd to repo directory

2. Install [Anaconda](https://www.anaconda.com/products/individual)

3. Create virtual environment (at time of writing cvxpy requires python 3.7)
```
conda create -n portfolio_opt python=3.7
conda activate portfolio_opt
pip install -r requirements.txt
```
    or
```
conda env create -f environment.yaml
conda activate portfolio_opt
```
4. Add environment to Jupyter
```
ipython kernel install --user --name=portfolio_opt
```
5. `jupyter notebook`

6. Run [Portfolio\ optimization.ipynb](Portfolio\ optimization.ipynb)