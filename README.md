# Norm of a matrix
## Aim
To write a program to find the 1-norm, 2-norm and infinity norm of the matrix and display the result in two decimal places.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
	1. Get the input matrix using np.array()   
    2. Find the 2-norm of the matrix using np.linalg.norm()
	3. Print the norm of the matrix in two decimal places.
## Program:
```Python
# Read matrix input
A = eval(input())

rows = len(A)
cols = len(A[0])

# Calculate column sums
max_sum = 0

for j in range(cols):
    col_sum = 0
    for i in range(rows):
        col_sum += abs(A[i][j])
    
    if col_sum > max_sum:
        max_sum = col_sum

print(f"{max_sum:.2f}")



# 2-Norm of a Matrix
'''
Program to find 2-norm of a matrix.
Developed by: srinikesh t
RegisterNumber: 212225040427
'''
import math

# Read matrix input
A = eval(input())

rows = len(A)
cols = len(A[0])

# Compute A^T * A
ATA = [[0 for _ in range(cols)] for _ in range(cols)]

for i in range(cols):
    for j in range(cols):
        s = 0
        for k in range(rows):
            s += A[k][i] * A[k][j]
        ATA[i][j] = s

# Find largest eigenvalue for 2x2 matrix
if cols == 2:
    a = ATA[0][0]
    b = ATA[0][1]
    c = ATA[1][0]
    d = ATA[1][1]

    trace = a + d
    det = a * d - b * c

    eigen1 = (trace + math.sqrt(trace * trace - 4 * det)) / 2
    eigen2 = (trace - math.sqrt(trace * trace - 4 * det)) / 2

    largest = max(eigen1, eigen2)

    l2_norm = math.sqrt(largest)

    print(f"{l2_norm:.2f}")




# Infinity Norm of a Matrix
# Read matrix input
A = eval(input())

max_sum = 0

# Find maximum row sum
for row in A:
    row_sum = 0
    for val in row:
        row_sum += abs(val)
    
    if row_sum > max_sum:
        max_sum = row_sum

print(f"{max_sum:.2f}")




```
## Output:
### 1-Norm of a Matrix
<img width="1212" height="312" alt="image" src="https://github.com/user-attachments/assets/d6c3f6e8-61a5-4877-8ed4-f165060fefc6" />


### 2-Norm of a Matrix
<img width="1222" height="378" alt="image" src="https://github.com/user-attachments/assets/aa54cb91-b3b6-4a27-82e1-a315bec719c2" />


### Infinity Norm of a Matrix
<img width="1220" height="337" alt="image" src="https://github.com/user-attachments/assets/6b05d7e2-283b-42d6-a38a-773b72ce63e4" />

## Result
Thus the program for 1-norm, 2-norm and Infinity norm of a matrix are written and verified.
