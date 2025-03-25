# Exp:8 Hamming-Shannon-fano
# Name: Sri Yogavarshini R
# Reg no.: 212223060270
# Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output.
# Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

### Aim:

To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

### Tools Required:

python IDE with Numpy and Scipy.

### Program:
```python
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
### Calculation:

![image](https://github.com/user-attachments/assets/01c0f7e5-51e7-4038-aada-00a8f9a93df1)

![WhatsApp Image 2025-03-25 at 21 25 01_7534e99c](https://github.com/user-attachments/assets/d5d141c9-f871-41f7-ac8e-fbdfcda047f4)

![WhatsApp Image 2025-03-25 at 21 25 01_4472172c](https://github.com/user-attachments/assets/f079fe2c-d2bd-4f46-a50b-c6a22c2f8cbc)

![WhatsApp Image 2025-03-25 at 21 24 59_2727c457](https://github.com/user-attachments/assets/54e84261-346c-4712-a057-2f70b4334b9d)

![WhatsApp Image 2025-03-25 at 21 25 00_08c8d47a](https://github.com/user-attachments/assets/f02cfe2a-70b2-4d1a-9765-542f5fefcecc)

### Result:

For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25
Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484.
