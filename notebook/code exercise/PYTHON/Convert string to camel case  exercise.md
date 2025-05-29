---
type:
  - Regular Expressions
  - Algorithms
  - Strings
tags:
  - "#programming_exercise"
---
### introduction
Complete the method/function so that it converts dash/underscore delimited words into ==camel casing==. The first word within the output should be capitalized ***==only==*** if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case). The next words should be always capitalized.
#### Examples

`"the-stealth-warrior"` gets converted to `"theStealthWarrior"`

`"The_Stealth_Warrior"` gets converted to `"TheStealthWarrior"`

`"The_Stealth-Warrior"` gets converted to `"TheStealthWarrior"`

---
### my solution
```python
def to_camel_case(text:str):
    strin =''
    num=0
    up = False
    for i in range(len(text)):    
        if text[i] == '-' or text[i] == '_':  
            strin = strin.replace(text[i],'')
            up = True
            if up:
                num = i+1
        else:
            if up:
                strin += text[num].upper()
                up = False
                continue
            strin += text[i]
    return strin
```

### others' solutions

```python

def to_camel_case(text):
    removed = text.replace('-', ' ').replace('_', ' ').split()
    if len(removed) == 0:
        return ''
    return removed[0]+ ''.join([x.capitalize() for x in removed[1:]])
```


```python
def to_camel_case(text):
    return text[:1] + text.title()[1:].replace('_', '').replace('-', '')
```

```python
import re
def to_camel_case(text):
    return re.sub('[_-](.)', lambda x: x.group(1).upper(), text)
```

```python
from re import compile as reCompile
PATTERN = reCompile(r'(?i)[-_]([a-z])')
def to_camel_case(text):
    return PATTERN.sub(lambda m: m.group(1).upper(), text)
```


```python
def to_camel_case(text):
    return \
     text[0] + ''.join([w[0].upper() +\
     w[1:] for w in text.replace("_", "-").split("-")])[1:] if text else ''
```