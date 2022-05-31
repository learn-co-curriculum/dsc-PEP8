# PEP8 and PEP257

## Introduction

PEP stands for Python Enhancement Proposals. Check them out [here](https://www.python.org/dev/peps/)! We'll start by talking about PEP8, which is the Style Guide for Python code. This discusses many points which are also important for collaboration. Git is useful for sharing and integrating code bases, but if code is poorly written it can still be cryptic and difficult to decipher. By following styling guidelines such as those outlined in PEP8, we can all create more legible code that can be shared in a streamlined fashion.

## Objectives

You will be able to:

- List the conventions defined in PEP8 

## PEP8 Introductory notes

Remember that the guidelines in PEP8 are just that: guidelines. The main goal is to make code more readable. Often, projects may have their own style guidelines which should take precedence. Most important of all is consistency. Be consistent with how you format your code and stick to it. With that, here's an overview of some of the most important guidelines from the PEP8 document to start familiarizing yourself with.

## Whitespace

1. Avoid trailing whitespace; its hard to see!
2. Always use whitespace on either side of binary operators like `=`, `==`, `!=`, `>`, `<`, `<=`, `not`, `in`, `and`, `or` ...
3. If operators with different priorities are used, consider adding whitespace around the operators with the lowest priority(ies). For example, multiplication takes precedence over addition, so we might not include whitespace around the multiplication, helping to indicate that these operations happen first and form a cohesive group.

### Good whitespace usage


```python
i = 1
i = i + 1
i += 1
x = i*2 - 1
hypot2 = x*x + i*i
c = (x+x) * (i-i)
```

### Bad whitespace usage


```python
i=1
i=i+1
i +=1
x = i * 2 - 1
hypot2 = x * x + i * i
c = (x + x) * (i - i)
```

## Line length

As a general rule of thumb, limit all lines of code to 79 characters.


```python
# Below is a verbose list comprehension that is 79 characters long as a silly example
[integer**2+1 for integer in range(1,100) if integer > 20 and integer % 5 == 0]
```

## Variable names

1. Never use the characters 'l' (lowercase letter el), 'O' (uppercase letter oh), or 'I' (uppercase letter eye) as single character variable names.
     1. In some fonts, these characters are indistinguishable from the numerals one and zero. When tempted to use 'l', use 'L' instead.  
2. Don't use built-in Python keywords like `list`, `dict` or `str` as variable names: this is not only a style guideline, it will break your code! 

## Indentation

The importance of indentation in Python was introduced in the conditionals lesson. Here are the conventional style guidelines that should be followed:

1. When indenting, use 4 spaces instead of a tab.
    1. Note that Python 3 disallows mixing the use of tabs and spaces for indentation. At some point you'll encounter this error: be on the lookout!
2. Vertically align continuation lines of code.
    1. This gets used for long functions, lists or conditionals

Here are some examples using functions. Functions will be introduced formally in the future so don't worry if the syntax looks unfamiliar. Just keep in mind that there are style conventions associated with functions. Comments have been placed in the code to help guide understanding.

### Good Indentation


```python
# Add 4 spaces (an extra level of indentation) to distinguish arguments from the rest 
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)
    
# Aligned with opening delimiter 
foo = long_function_name('var_one', 'var_two',
                         'var_three', 'var_four')
```

### Bad Indentation


```python
# Further indentation required as indentation is not distinguishable 
def long_function_name(
    var_one, var_two, var_three,
    var_four):
    print(var_one)

# Arguments on first line forbidden when not using vertical alignment 
foo = long_function_name('var_one', 'var_two',
    'var_three', 'var_four')
```

Somewhat similarly, when using operations, keep the operator with the operand:

### Good operator placement 


```python
# Note: this line of code will produce an error (the variables referenced have not been defined)
income = (gross_wages
          + taxable_interest
          + (dividends - qualified_dividends)
          - ira_deduction
          - student_loan_interest)
```

### Bad operator placement


```python
# Note: this line of code will produce an error (the variables referenced have not been defined)
income = (gross_wages +
          taxable_interest +
          (dividends - qualified_dividends) -
          ira_deduction -
          student_loan_interest)
```

### PEP 257 - Docstring Conventions

There are also recommendations for how to format your docstrings. But first, what is a docstring? A docstring is a string literal (AKA fixed value) that occurs as the first statement in a module, function, or method definition. Recall that a function should ideally only perform one action. A docstring of a function should tell you simply what it does and some description of the arguments it takes and the output You can see an example below:

#### One-line Docstring


```python
# Example of a one-line docstring for a function. a one-line description
# is sufficient for a relatively simple function.

def add_one(number):
    """
    add_one() takes an integer, float and returns that value 
    added by one.
    """
    number_plus_one = number + 1
    return number_plus_one
        
```

#### Multi-line Docstring


```python
# Example of a multi-line docstring. If your function has some complexity
# a more descriptive docstring is recommended that includes descriptions
# of the function arguments and outputs like so.

def add_two(number):
    """
    add_two() takes an integer, float and returns that value 
    added by one.
    
    Arguments: number - a single integer or float.
    
    Returns:   number_plus_two - the sum of the given integer or float and 
               two.
    """
    number_plus_one = number + 1
    return number_plus_one
        
```

You have accessed the docstrings of functions before by using the `help()`
command. This is the process how those are written! lets take a look at the ways we can access docstrings of functions.

**Remember that when calling the help command and you want the docstring of the function, to pass the `help()` function the name of your function,  without the parentheses!**


```python
# 1.) By using the help() command.
help(add_one)
help(add_two)
```

### Why is this important?

In Data Analytics and the Data Science fields... You will likely be performing repeat tasks, usually in cleaning and formatting data for analysis. Although not all analysts use Python, it is an incredibly powerful and versatile tool when undertaking any analysis. Its also a highly-demanded skill!

It is typical for professionals in these fields to write functions they will use often in a python file. This file would have a `.py` extension and you would be able to use functions written in it just like you use those in the libraries you have used thus far. Those libraries are just `.py` files! This is how any library is written. You may share this file with collaborators or make it open-source (available to the public on a platform like github). In any case, when sharing code READABILITY and CLARITY are gold. thats why it is good to hold to the PEP 8 and PEP 257 conventions.

## Additional Resources

* [PEP Website](https://www.python.org/dev/peps/)
* [PEP8 Page](https://www.python.org/dev/peps/pep-0008/)
* [PEP257 Page](https://www.python.org/dev/peps/pep-0257/)
* [Numpy Style Guide for Docstrings](https://numpydoc.readthedocs.io/en/latest/format.html)

The above is a good resource on specifics about docstrings for functions that are concerned with computation.

## Summary

Today we introduced you to Python Enhancement Proposals (PEPs), documents for the Python community meant to describe new features or processes. Specifically, we discussed some of the contents of PEP8, the style guide for Python. Following these guidelines will lead to more readable code that can be shared with collaborators. With that, let's leave you with a poem of sorts: PEP20!

PEP 20 -- The Zen of Python: 


```python
import this
```
