# Python
Ample samples of Python
TaylorAnalyses
```python
# Created on iPad.
import numpy as np
import math
#计算n级泰勒公式的误差率
def factorial(num):
    if num == 1 or num == 0:
        return 1
    else:
        return num * factorial(num - 1)
#平均误差
def err(ob,pre,distance):
    return np.abs(ob - pre)/distance
obfun		= lambda x:np.e**x
error_edgeL = int(input("请输入函数范围的左端点"))
error_edgeR = int(input("请输入函数范围的右端点"))
distance 	= np.abs(error_edgeR - error_edgeL)
n 			= int(input("展开最高次数"))
sum   = 0
exact = 0
for x in range(error_edgeL,error_edgeR+1):
    exact = obfun(x) + exact
    tlfun = 1
    for i in range(1,n+1):
    		tlfun += x**i / factorial(i)
    sum += tlfun
print("平均误差为"err(sum,exact,distance))
```
