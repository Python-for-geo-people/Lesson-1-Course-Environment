## Sources
This tutorial is based on a the [Software Carpentry group's](http://software-carpentry.org/) lessons on [Programming with Python](http://swcarpentry.github.io/python-novice-inflammation/).

## Getting started
1. We can start by opening a new IPython window. To do this, double-click on the IPython icon on the Desktop. You should see a new terminal window appear that looks like the one below.

    ![IPython window](../img/IPython.png)

Now we are ready to start.

## Variables, arithmetic and libraries
We will start our Python lesson by learning a bit of the basic operations you can perform using Python.

1. Python can be used as a simple calculator.

    ```python
    >>> 1 + 1
    2
    >>> 5 * 7
    35
    ```

2. You can use Python for more advanced math by using *functions*. Functions are pieces of code that perform a single action such as printing information to the screen (e.g., the `print()` function). Functions exist for a huge number of operations in Python.

    ```python
    >>> sin(3)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'sin' is not defined
    >>> sqrt(4)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'sqrt' is not defined
    ```

    Wait, what? Python can't calculate square roots or do basic trigonometry? Of course it can, but we need one more step.

3. The list of basic arithmetic operations that can be done by default in Python is in the table below.

    | Operation      | Symbol | Example syntax | Returned value |
    | -------------- | ------ | ---------------|----------------|
    | Addition       | `+`    | `2 + 2`        | `4`            |
    | Subtraction    | `-`    | `4 + 2`        | `2`            |
    | Multiplication | `*`    | `2 * 3`        | `6`            |
    | Division       | `/`    | `4 / 2`        | `2`            |
    | Exponentiation | `**`   | `2**3`         | `8`            |
For anything more advanced, we need to load a *library*.

    ```python
    >>> import math
    >>> math.sin(3)
    0.1411200080598672
    >>> math.sqrt(4)
    2.0
    ```
A *library* is a group of code items such as functions that are related to one another. Libraries are loaded using `import`. Functions that are part of the library `libraryname` could then be used by typing `libraryname.functionname()`. For example, `sin()` is a function that is part of the `math` library, and used by typing `math.sin()` with some number between the parentheses.
4. Functions can also be combined.

    ```python
    >>> print(math.sqrt(4))
    2.0
    >>> print('The square root of 4 is',math.sqrt(4))
    The square root of 4 is 2.0
    ```

5. *Variables* can be used to store values calculated in expressions and used for other calculations.

    ```python
    >>> weight_kg = 55
    >>> print(weight_kg)
    55
    >>> print('weight in pounds:', 2.2 * weight_kg)
    weight in pounds: 121.0
    ```
Above, we also see one common format for *good* variable naming, separation of words by underscores `_` (e.g., `weight_kg`). This is called pothole_case_naming. We'll see another below.

6. Values stored in *variables* can also be updated.

    ```python
    >>> weight_kg = 57.5
    >>> print('weight in kilograms is now:', weight_kg)
    weight in kilograms is now: 57.5
    >>> WeightInPounds = 2.2 * weight_kg
    >>> print('weight in kilograms:', weight_kg, 'and in pounds:', WeightInPounds)
    weight in kilograms: 57.5 and in pounds: 126.5
    ```
An alternative to naming variables using pothole_case_naming is to use capital letters for each word with no spaces between (e.g., `WeightInPounds`). This is called CamelCaseNaming. Both options are easy to read and help you use *good* variable names. After all, *people* should be able to easily understand what different variables contain :+1:.

7. Note that changing the values of a variable does not affect those of other variables.

    ```python
    >>> weight_kg = 100.0
    >>> print('weight in kilograms is now:', weight_kg, 'and weight in pounds is still:', WeightInPounds)
    weight in kilograms is now: 100.0 and weight in pounds is still: 126.5
    ```

8. One of nice options in IPython is that you can see which variables are in memory by typing `whos`.

    ```python
    >>> whos
    Variable         Type     Data/Info
    -----------------------------------
    WeightInPounds   float    126.50000000000001
    weight_kg        float    100.0
    ```

9. There are 4 basic *data types* in Python as shown in the table below.

    | Data type name | Data type            | Example         |
    | -------------- | -------------------- | --------------- |
    | `int`          | Whole integer values | `4`             |
    | `float`        | Decimal values       | `3.1415`        |
    | `str`          | Character strings    | `'Korvapuusti'` |
    | `bool`         | True/false values    | `True`          |
The data types are displayed when using `whos`, but can also be found using the `type()` function. As you will see, the data types are important because some are not compatible with one another.

    ```python
    >>> FavoriteTreat = 'Korvapuusti'
    >>> type(FavoriteTreat)
    str
    >>> type(WeightInPounds)
    float
    >>> WeightInPounds = WeightInPounds + 100.0 * FavoriteTreat
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: can't multiply sequence by non-int of type 'float'
    ```
