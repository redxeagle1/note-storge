---
type:
  - Strings
  - Fundamentals
tags:
  - programming_exercise
---
### introduction
Your task is to convert strings to how they would be written by Jaden Smith. The strings are actual quotes from Jaden Smith, but they are not capitalized in the same way he originally typed them.

Example:

```
Not Jaden-Cased: "How can mirrors be real if our eyes aren't real"
Jaden-Cased:     "How Can Mirrors Be Real If Our Eyes Aren't Real"
```

### my solution
***==NOTHING SOLVED==***
### others's solution

```python 
def to_jaden_case(string):
    return ' '.join(word.capitalize() for word in string.split())
```

```python
def to_jaden_case(string):
    list = string.split()
    new_list = [i.capitalize() for i in list]
    return ' '.join(new_list)
```


```python
def to_jaden_case(string):
    words = string.split(" ")
    output = ""
    for word in words:
        corrected = word.capitalize()
        output += corrected + " "        
    return output[0:-1]
```


```python   
def to_jaden_case(string):
    ''' Split the input string into a list of words
    The split() method without any arguments splits on whitespace'''
    words = string.split()
    '''Use a list comprehension to create a new list where each word
    from the original list is capitalized
    The capitalize() method capitalizes the first letter of a string
    and makes all other characters in the string lowercase'''
    capitalized_words = [word.capitalize() for word in words]
    ''' Join the list of capitalized words back into a single string
    with a space character (' ') in between each word'''
    result = ' '.join(capitalized_words)
    # Return the resulting string
    return result
```
```python
def to_jaden_case(string : str):
    words = string.split()
    new_list = [e.capitalize() for e in words]
    return ' '.join(new_list)
tester = "Trees Are Never Sad Look At Them Every Once In Awhile They'Re Quite Beautiful"
print(to_jaden_case(tester))
' '.join()
```