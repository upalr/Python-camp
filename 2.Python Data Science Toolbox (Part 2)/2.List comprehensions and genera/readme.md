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


# 2 Advanced comprehensions
## 2.1 Conditionals in Comprehensions

### 2.1.1 Conditionals on The Iterable 
![5.conditionsls-on-the-iterable.PNG](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/2.List%20comprehensions%20and%20genera/images/5.conditionsls-on-the-iterable.PNG)

### 2.1.2 Conditionals on The Output Expression 
![6.conditionals-on-the%20output-expressin.PNG](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/2.List%20comprehensions%20and%20genera/images/6.conditionals-on-the%20output-expressin.PNG)


## 2.2 Dict comprehensions
![7.dict-comprehension.PNG](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/2.List%20comprehensions%20and%20genera/images/7.dict-comprehension.PNG)

Another Example: 

```python
# Create a list of strings: fellowship
fellowship = ['frodo', 'samwise', 'merry', 'aragorn', 'legolas', 'boromir', 'gimli']

# Create dict comprehension: new_fellowship
new_fellowship = {member : len(member) for member in fellowship}

# Print the new list
print(new_fellowship)
```

# 3 Intorduction to Generator Expressions

## 3.1 Generator Expressions

![7.dict-comprehension.PNG](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/2.List%20comprehensions%20and%20genera/images/7.dict-comprehension.PNG)

## 3.2 List Comprehensions vs Generators

A generator is like a list comprehension except **it doesn't store the list in memory**. **it doesn't construct the list**, but it's an object we iterate over to produce **elements** of the **list(analogous list)** as required. 

Here we can see that looping over a generator expression produces the elements of the analogous list.

![7.dict-comprehension.PNG](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/2.List%20comprehensions%20and%20genera/images/7.dict-comprehension.PNG)

We can also pass a generator to the function **list()** to create the list 





