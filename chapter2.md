## 算法导论- 第二章 算法基础

### 插入排序

- 循环不变式性质

1.初始化：循环的第一次迭代之前，它为真；

2.保持：如果循环的某地迭代之前它为真，那么下次迭代之前它仍为真；

3.在循环终止时，不变石为我们提供一个有用的性质，该性质有助于证明算法是正确的。


- 插入排序python实现

``` 

## insertion-sort 
def sort1(data, descend = False):
    for j in range(len(data)-1):
        key = data[j+1]
        i = j
        if des:cend == True:
            while i>=0 and data[i]<key:
                data[i+1] = data[i]
                i -= 1
        else:
            while i>=0 and data[i]>key:
                data[i+1] = data[i]
                i -= 1
        data[i+1] = key
        
data = [1, 4, 5, 3, 2]
print  'data:',data
sort1(data, descend=False) 
print 'sorted:',data
output:
data: [1, 4, 5, 3, 2]
sorted: [1, 2, 3, 4, 5]
```

- 2.1-4 A ,B 为二进制整数，位数为n， 相加结果以二进制存储C中，n+1 位。

```
import random 
import numpy as np
n = 5
random.seed(1)
# create two binary variable
A = [random.randint(0, 1) for _ in range(n)]
B = [random.randint(0, 1) for _ in range(n)]
print 'A:',A 
print 'B:', B

def add1(A, B):
    if len(A) != len(B):
        print "please inpute the same length two array"
    else: 
        C = np.repeat(0, len(A)+1)
        i = len(A)-1
        while i >=0:
            C[i+1] = A[i] + B[i] + C[i+1]
            if C[i+1] >1:
                C[i] += 1
                C[i+1] -=2
            i -= 1    
        print 'C:',C
add1(A, B)    
  OUTPUT: 
A: [0, 1, 1, 0, 0]
B: [0, 1, 1, 0, 0]
C: [0 1 1 0 0 0]   
```
- 2.2-2 选择算法python实现
```
def select_algroithm(data):
    for i in range(len(data)):
        min = data[i]
        for j in range(len(data)-i-1):
            index = i
            if data[j+1+i] < min:
                min = data[j+1+i]
                index = j + 1 + i
            data[index] = data[i]
            data[i] = min
data = [3, 11, 5, 9, 0] 
print 'origal data:', data
select_algroithm(data)
print 'ordered data:',data

output:
origal data: [3, 11, 5, 9, 0]
ordered data: [0, 3, 5, 9, 11]
```
### 分治算法

- 冒泡算法python实现
```
def  bubble_sort(data):
    listLength = len(data)
    for i in range(listLength, 1, -1):
        for j in range(i-1):
            if data[j] > data[j+1]:
                data[j], data[j+1] = data[j+1], data[j]
    print 'sorted data:', data            


if __name__ == '__main__':  
        data = [3, 4, 1, 2, 5, 8, 0]  
        print 'data:', data
        bubble_sort(data)
output:
data: [3, 4, 1, 2, 5, 8, 0]
sorted data: [0, 1, 2, 3, 4, 5, 8]
```
