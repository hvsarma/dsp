# Learn Python

Read Allen Downey's [Think Python](http://www.greenteapress.com/thinkpython/) for getting up to speed with Python 2.7 and computer science topics. It's completely available online, or you can buy a physical copy if you would like.

[![Think Python](img/think_python.png)](http://www.greenteapress.com/thinkpython/)

For quick and easy interactive practice with Python, many people enjoy [Codecademy's Python track](http://www.codecademy.com/en/tracks/python). There's also [Learn Python The Hard Way](http://learnpythonthehardway.org/book/) and [The Python Tutorial](https://docs.python.org/2/tutorial/).

Complete the following exercises to check your ability with Python.

These exercises are implemented with doctests, which are runnable tests inside docstrings. Fill in the function definitions. Correct solutions will make it possible to run (for example) `python -m doctest strings.py` with no messages about failures.

 * [Strings](python/strings.py)
 * [Lists](python/lists.py)


---

How are Python lists and tuples similar and different? Which will work as keys in dictionaries? Why?

> Lists and tuples are similar, as they both are accessible by indices.

> Lists are mutable, have an order, and have methods (e.g. .append()).

> Tuples are immutable, have a structure and have no method. Hence, used as keys in dictionaries.

---


---

How are Python lists and sets similar and different? Give examples of using both. How does performance compare between lists and sets for finding an element. Why?

> Set is a dictionary with no values. Set is an unordered unduplicate collection of list elements.
```bash
>>> gender = ['male', 'female', 'male', 'male']
>>> set(gender)
set(['male', 'female'])
```
> Set needs to be en'listed' before accessing its content.
e.g. list(set(gender))



---


---

Describe Python's `lambda`. What is it, and what is it used for? Give at least one example, including an example of using a `lambda` in the `key` argument to `sorted`.

> Lambdas are python's inline functions, which can take 1 expression only. Lambdas avoid function calling on the go, hence frees up stack memory.

> Example of a lambda function I used in list exercise: 
`sorted(tuples,key=lambda tuples: tuples[1])`
This sorts a tuple by its second element

---


---

Explain list comprehensions. Give examples and show equivalents with `map` and `filter`. How do their capabilities compare? Also demonstrate set comprehensions and dictionary comprehensions.

> List comprehension is an elegant way to define and create list in Python. These lists have often the qualities of sets, but are not in all cases sets.

> List comprehension is a complete substitute for the lambda function as well as the functions map(), filter() and reduce(). For most people the syntax of list comprehension is easier to be grasped. 

> Below is an example of filtered list comprehension. `[hex(n) for n in range(0, 100) if n > 20]`. This compares with the map example such as `list(map(hex, filter(lambda x: x > 20, range(0, 100))))`.

> A set comprehension is similar to a list comprehension, but returns a set and not a list. Syntactically, we use curly brackets instead of square brackets to create a set. Sets have only values, instead of k:v pairs, as in dictionary comprehension. Example of set comprehension would be: `{i for i in set(range(26))}`

> Dict comprehensions are just like list comprehensions, except that we group the expression using curly braces instead of square braces. Example of dict comprehension would be: `{i : chr(65+i) for i in range(26)}`


---


Write a Markov text generator, [markov.py](python/markov.py). Your program should be called from the command line with two arguments: the name of a file containing text to read, and the number of words to generate. For example, if `chains.txt` contains the short story by Frigyes Karinthy, we could run:

```bash
./markov.py chains.txt 40
```

A possible output would be:

> show himself once more than the universe and what I often catch myself playing our well-connected game went on. Our friend was absolutely correct: nobody from the group needed this way. We never been as the Earth has the network of eternity.

There are design choices to make; feel free to experiment and shape the program as you see fit. Jeff Atwood's [Markov and You](http://blog.codinghorror.com/markov-and-you/) is a fun place to get started learning about what you're trying to make.
