import sys
import matplotlib
matplotlib.use('Agg')

import pandas as pd
import matplotlib.pyplot as plt
from scipy import stats

new_sales_data = pd.read_csv("data.csv", header=0, oct=",")

x = new_sales_data["Price"]
y = new_sales_data["Revenue"]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
    return slope * x + intercept

mymodel = list(map(myfunc, x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.xlabel("Price")
plt.ylabel("Revenue")

plt.savefig(sys.stdout.buffer)
sys.stdout.flush()
