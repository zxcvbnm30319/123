# 123

安安安

```py
from pulp import *

#設定Decision Variables
Ingredients=['BREAD','PEANUTBUTTER','StrawberryJelly','GrahamCracker','Milk','Juice']

CarloiesFat={'BREAD':10,'PEANUTBUTTER':75,'StrawberryJelly':0,'GrahamCracker':20,'Milk':70,'Juice':0}

totalCalories={'BREAD':70,'PEANUTBUTTER':100,'StrawberryJelly':50,'GrahamCracker':60,'Milk':150,'Juice':100}

VltaminC={'BREAD':0,'PEANUTBUTTER':0,'StrawberryJelly':3,'GrahamCracker':0,'Milk':2,'Juice':120}

Protein={'BREAD':3,'PEANUTBUTTER':4,'StrawberryJelly':0,'GrahamCracker':1,'Milk':8,'Juice':1}

costs={'BREAD':5,'PEANUTBUTTER':4,'StrawberryJelly':7,'GrahamCracker':8,'Milk':15,'Juice':35}

# Create the 'prob' variable to contain the problem data
prob = LpProblem("The cost Problem", LpMinimize)

# A dictionary called 'ingredient_vars' is created to contain the referenced Variables
ingredient_vars = LpVariable.dicts("Ingr",Ingredients,0)
a = LpVariable.dicts("a",Ingredients,0)
print(ingredient_vars)

#加入目標式
prob += lpSum([costs[i]*ingredient_vars[i] for i in Ingredients])
#prob += lpSum([Protein[i]*a[i] for i in Ingredients])

prob += lpSum(VltaminC[i]*ingredient_vars[i] for i in Ingredients)>=60 #至少60g維他命C
prob += lpSum(Protein[i]*ingredient_vars[i] for i in Ingredients)>=12#至少12G
prob += lpSum(totalCalories[i]*ingredient_vars[i] for i in Ingredients)<=600#全部熱量在400~600之間
prob += lpSum(totalCalories[i]*ingredient_vars[i] for i in Ingredients)>=400
#不超過30%熱量來自脂肪
prob += lpSum(totalCalories[i]*ingredient_vars[i] for i in Ingredients)*0.3>=lpSum(CarloiesFat[i]*ingredient_vars[i] for i in Ingredients)
prob += (ingredient_vars['Milk']+ingredient_vars['Juice'])>=1#牛奶或果汁至少一杯
prob += (ingredient_vars['BREAD'])==2#麵包至少2片
prob += (ingredient_vars['PEANUTBUTTER'])>=2*(ingredient_vars['StrawberryJelly'])#花生醬是草莓醬的兩倍

#求解
prob.solve()
#查看目前解的狀態
print("Status:", LpStatus[prob.status])

#印出解及目標值
for v in prob.variables():
    print(v.name, "=", v.varValue)
print('obj=',value(prob.objective))
```
# 123132
## 132
### 111 
#### 4568
>132
[GOOGLE 翻譯](https://translate.google.com.tw/?hl=zh-TW)

|123|4506|7800009|
|---|---:|:---:|
|5555555555|44444|12313218|


# 123
$$¥frac{¥sin(x)}{x}$$

$N(b,d)=(b-1)M$
