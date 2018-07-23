**Linear Regression with Python**
**1. Here's a way to calculate the basic Linear Regression:**
1. Import the necessary packages
```markdown
import pandas as pd
import numpy as np
```

2. Get the data in csv and explore the data
```markdown
df = pd.read_csv('linear-regression.csv', header=None)
df.columns = ['x','y']
df.head()
df.info
```

3. find constants and coefficient regression with x2, y2, and xy
3.a.
```markdown
df['x2'] = df['x'].map(lambda x: x*x)
df['y2'] = df['y'].map(lambda y: y*y)
df['xy'] = df['x'] * df['y']
df.head()
```
```markdown
print("(sum x) is", sum(df['x']))
print("(sum y) is",sum(df['y']))
print("(sum x2) is",sum(df['x2']))
print("(sum y2) is",sum(df['y2']))
print("(sum xy) is",sum(df['xy']))
```

3.b.
```markdown
Find constants (a)
a = ((sum y)(sum x2) - (sum x)(sum xy)) / (n(sum x2) - (sum x)**2)
a = (((393.93625*14.99537)-(-1.76185*37.66216))/((100*14.99537)-(-1.76185**2)))
print(a)
```

```markdown
Find coefficient regression (b)
b = (n(sum xy) - (sum x)(sum y))/(n(sum x2) - (sum x)**2)
b = (((100*37.66216)-(-1.761815*393.93625))/(100*14.99537-(-1.761815**2)))
print(b)
```

4. Write linear regression model
```markdown
from sympy import *
X = Symbol('x')
Y = Symbol('y')
Y = a + b*X
print(Y)
```

5. Run your model
```markdown
df['result'] = df['x'].map(lambda x: 2.96827972733361 * x + 3.97538363648389)
df.head()
```
