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

Products = ["Widget_A", "Widget_B", "Widget_C", "Gadget_X", "Gadget_Y", "Gadget_Z", "T-shirts_A", "T-shirts_B", "Pants_A"]
Units = [100, 60, 40, 120,75, 30, 150, 210, 120]
print(Products)
print(Units)

import pandas as pd

Data = {
    'Prdct_id': [110, 120, 130, 140, 150, 210, 220, 230, 240, 310, 320, 330, 410, 420, 430, 510, 520, 530, 610, 620, 630, 710, 720],
    'Prdct_name': ['Widget_A', 'Widget_B', 'Widget_C', 'Gadget_X', 'Gadget_Y', 'Gadget_Z', 'T-shirts_A', 'T-shirts_B', 'Pants_A', 'Pants_B', 'Books_A', 'Books_B', 'Tool_A', 'Tool_B', 'Food_A', 'Food_B', 'Drink_A', 'Drink_B', 'Toy_A', 'Toy_B', 'Home_A', 'Home_B'],
    'CATEGORY': ['Electronics', 'Electronics', 'Electronics', 'Electronics', 'Electronics', 'Electronics', 'Apparel', 'Apparel', 'Apparel', 'Apparel', 'Books', 'Hardware', 'Hardware', 'Hardware', 'Grocery', 'Grocery', 'Grocery', 'Grocery', 'Toys', 'Toys', 'Home', 'Home'],
    'PRICE': [15.99, 25.99, 35.99, 45.99, 29.99, 39.99, 49.99, 14.99, 19.99, 34.99, 32.99, 49.99, 24.99, 54.99, 6.99, 2.99, 19.99, 22.99, 3.99, 65.99, 79.99, 69.99],
    'Units_sold': [75, 50, 120, 60, 80, 150, 200, 100, 80, 300, 250, 50, 40, 500, 800, 1000, 400, 150, 120, 300, 40],
    'Revenue': [1499.00, 3399.50, 5619.70, 3969.40, 1198.50, 2387.70 5891.00, 2729.00, 2559.30, 3897.00, 3987.50, 3996.00, 3749.25, 3249.50, 2349.60, 1995.00, 2392.00, 3598.80, 2997.00, 2999.50, 2399.70, 2799.60],
    'PROFIT': [400.00, 850.00, 400.00, 300.00, 600.00, 800.00, 350.00, 900.00, 1000.00, 1200.00, 600.00, 500.00, 400.00, 400.00, 400.00, 600.00, 500.00, 400.00, 600.00, 500.00, 400.00]
}

df = pd.DataFrame(Data)

print(df)

import pandas as pd
import numpy as np

Price = [18, 20, 35, 50, 49, 55, 59, 29, 24, 25, 34, 12, 15, 9, 49, 64, 74, 3, 2, 1, 4, 19, 29, 9, 59, 79, 69]

print ('Ең қымбат өнім бағасы:', max(Price))
print ('Ең арзан өнім бағасы:', min(Price))
print ('Өнімдердің бағасының орташа мәні:',np.mean(Price))
