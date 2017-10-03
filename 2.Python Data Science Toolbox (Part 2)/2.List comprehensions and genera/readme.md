# 1. List Comprehensions

[Lsit Comprehension DataCamp](https://campus.datacamp.com/courses/python-data-science-toolbox-part-2/list-comprehensions-and-generators?ex=1)

## 1.1 List comprehension Example 
**Syntex** : [[output expression] for iterator variable in iterable]

![1.list-comprehension.PNG](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/2.List%20comprehensions%20and%20genera/images/1.list-comprehension.PNG)


## 1.2 List comprehension Syntex Comparison  

![2.list-comprehension-syntex.PNG](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/2.List%20comprehensions%20and%20genera/images/2.list-comprehension-syntex.PNG)


## 1.3 Nested Loop Example  

![3.nested-loop.PNG](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/2.List%20comprehensions%20and%20genera/images/3.nested-loop.PNG)


## 1.4 Nested Loop List comprehension

![4.nested-loop-list-comprehension.PNG](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/2.List%20comprehensions%20and%20genera/images/4.nested-loop-list-comprehension.PNG)



## 1.5 Build This Using Nested List comprehension

```python
matrix = [[0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4]]
```
**Mind it**: [[output expression] for iterator variable in iterable]


```python
# Create a 5 x 5 matrix using a list of lists: matrix
matrix = [[col for col in range(5)] for row in range(5)]

# Print the matrix
for row in matrix:
    print(row)
```
