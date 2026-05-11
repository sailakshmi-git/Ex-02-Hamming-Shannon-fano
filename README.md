# Ex: 02 - Huffman - Shannon_fano
## AIM:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average codeword length, Entropy, Variance, Redundancy, Efficiency.

## TOOLS REQUIRED:
Python IDE with Numpy and Scipy.

## PROGRAM:

```
import numpy as np
import math

L = 0
hs = 0
p = []
lk = []

n = int(input("Enter the number of Samples: "))

for i in range (n):
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))
    p.append(pr)

for j in range (n):
    l = float(input(f"Enter the length of the sample values {j + 1}: "))
    lk.append(l)

# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

# Efficiency
eff = hs / L
eff = round(eff,3)

# Redundancy
red = round(1 - eff, 3)

# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var, 3)

print(f"Average Codeword Length is: {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is: {red}")
print(f"Variance is: {var}")
```


## CALCULATION:


<img width="997" height="1600" alt="image" src="https://github.com/user-attachments/assets/22d4ed34-f960-47f8-8a0a-d8c3fb44550f" />


<img width="1080" height="938" alt="image" src="https://github.com/user-attachments/assets/3ea6d216-c980-48e6-bd6a-0d15999e8825" />


## OUTPUT:

<img width="1166" height="527" alt="image" src="https://github.com/user-attachments/assets/a5907a36-0890-4e24-975e-7eb52103dcf4" />

## RESULT:
The Huffman and Shannon-Fano of the given statistics {} using python are verified.
