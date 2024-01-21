# Python

## Monte Carlo Simulation Using NumPy

What are the chances I'll get a total roll of 15 or higher if I roll 3 six-sided dice?

Adapted from: https://www.youtube.com/watch?v=slbZ-SLpIgg

```python
import numpy as np
import matplotlib.pyplot as plt

sims = 1000000
A = np.random.uniform(1, 6, sims)
B = np.random.uniform(1, 6, sims)
C = np.random.uniform(1, 6, sims)

duration = A + B + C

plt.figure(figsize = (3, 1.5))
plt.hist(duration, density = True)
plt.axvline(15, color = 'r')
plt.show()
```
