# Module 01 - Basics 2

## Comment:
This second module is the evolution of two original projects created by the
Paris-based student association 42 AI.
They are named Bootcamp Python and Bootcamp Machine Learning.
active members of 42 AI re-designed both of them for the school curriculum.

Bootcamps has been developped between August 2019 and March/April 2020.
Active 42AI members organized severals sessions of 2 weeks to 42Paris students
to offer them the possibility to get famliar with Python and basics concepts
of machine learning.
  
The success of those sections brings the pedagogy to accept the idea to integrate
the 2 bootcamps to the curriculum (initial discussion (01-05/2019) with 42 Paris
pedago team	highlighted a categorical opposition/refusal to this idea)
  
The transcription had been realized over the direction of Matthieu David.
Several 42AI members contributed to the redaction on the correction scales.
For futur corrections on the scale, please contact the 42AI association via
contact@42ai.fr or the current 42AI pedagogical supervisor.

## Introduction
The Bootcamp Python and Bootcamp Machine Learning were originally created by
[42AI](https://github.com/42-AI) active members and were adapted to 'piscine'
format for the school 42 curriculum.
For any issue or suggestion: [42Paris](https://github.com/42-AI/bootcamp_python/issues) and
[42AI](https://github.com/42-AI/bootcamp_machine-learning/issues).

As usual, you have to observe the following courtesy rules:

- Remain polite, courteous, respectful, and constructive throughout the
evaluation process. The well-being of the community depends on it.

- Identify with the evaluated person or group the eventual dysfunctions of
the assignment. Take the time to discuss and debate the problems you may
have identified.

- You must consider that there might be some differences in the
understanding of and approach to project instructions, and the scope of
its functionalities, between you and your peers. Always remain open-minded
and grade them as fairly as possible. The pedagogy is valid only and only
if peer-evaluation is conducted seriously.

The goal of this module is to get started with the Python language.
You will study objects, classes, inheritance, built-in functions, magic methods,
generator ...

## Disclaimer
The serie of modules started to be produce at the time of the release of
Python 3.7. Students are free to use later version of Python as long as they
verified the producted code complies with all the aspects precised in the
subjects.
As a consequence we recommend to students to perform the modules with the
the Python version 3.7 (but this is just an advice).
Version can be checked with the command ```python -V```.

## guidelines
General rules
- Only grade the work that is in the student or group's GiT repository.

- Double-check that the GiT repository does belong to the student.
Ensure that the work is the one expected for the corrected exercise
and don't forget to verify that the command "git clone" is run in an empty
folder.

- Check carefully that no malicious aliases were used to make
you evaluate files that are not from the official repository.

- To avoid any surprises, carefully check that both the evaluating
and the evaluated students have reviewed the possible scripts used
to facilitate the grading.

- If the evaluating student has not completed that particular
project yet, it is mandatory for them to read the
entire subject prior to starting the defense.

- Use the flags available on this scale to signal an empty repository,
non-functioning program, a Norm error (specified next in general rules),
cheating, and so forth.
In these cases, the grading is over and the final grade is 0,
or -42 in case of cheating. However, except the exception of cheating, you
are encouraged to continue to discuss your work even if the later is in
progress in order to identify any issues that may have caused the project
failure and avoid repeating the same mistake in the future.

- Use the appropriate flag.

- Remember that for the duration of the defense, no other unexpected,
premature, or uncontrolled termination of the program, else the final
grade is 0.
  
- You should never have to edit any file except the configuration file if
the latter exists. If you want to edit a file, take the time to explain why
with the evaluated student and make sure both of you agree on this.

- The Norm: You will follow the PEP 8 standards.

- The function eval is never allowed.

- Your exercises are going to be evaluated by other students,
make sure that your variable names and function names are appropriate and civil.

- THE ERROR HANDLING WILL NOT BE PERFECT, IF THE CODE SHOWS THE USER IS AWARE OF THE POSSIBILITY AND HANDLED IT BY RAISING AN ERROR, PRINTING A MESSAGE AND EXITING OR RETURNING NONE IT IS CONSIDERED VALID. IF AN ABSURD VALUE IS RETURNED IT IS NOT VALID   

# Exercise 0: 'Exercise 00 - The Book'
## Description:
The goal of the exercise is to get you familiar with the notions of
classes and the manipulation of the objects related to those classes.

## Questions:
- **'Error management and basic tests'**\
  There are 2 classes, Book in book.py and Recipe in recipe.py.
  A Book object stores and manages Recipe.
  With the help of the test.py file, carry out at least the following tests
  to try to stress the error management:

	In the terminal:
	```bash
	python3
	```
	```python
	from book import Book
	from recipe import Recipe
	```
  - ## Recipe:
	```python
	Recipe("cooki", 0, 10, ["dough", "sugar", "love"], "deliciousness incarnate", "dessert")
	# Should print an error because cooking_lvl < 1

	Recipe("cooki", 1.5, 10, ["dough", "sugar", "love"], "deliciousness incarnate", "dessert")
	# Should print an error because cooking_lvl is not an int
	# OR
	# cooking lvl should be converted to an int somewhere

	Recipe("cooki", 1, 10, [], "deliciousness incarnate", "dessert")
	# Should print an error because empty ingredients

	Recipe("cooki", 1, 10, ["dough", "sugar", "love"], "deliciousness incarnate", "dessert")
	print("Congratulations you finally made sime delicous cookies")
	```
  - ## Book:
  - After the initialization of a correct Book object, verify:
	```python
	b = Book("My seductive recipes")
	print(b.creation_date)
	# should be the current date and time
	print(b.last_update)
	# should be the same as the creation date or None
	```                    
  - **get_recipe_by_name()** tests:
	```python
	crumble = Recipe("Crumble" , 1, 25, ["apples", "flour", "sugar"], "dessert" ,"delicious")
	b.add_recipe(crumble)
	print(b.last_update)
	# Should be different than the previous one

	b.get_recipe_by_name("Crumble")
	# should print the recipe
	# AND
	# <Recipe object at x>

	b.get_recipe_by_name("Liver Icecream")
	# The recipe does not exist
	# The error must be handled in a justifiable manner
	# such as returning None, [], or printing an error message
	```
  - **get_recipes_by_types()** tests: 
  
	```python
	print(b.get_recipes_by_types("dessert")[0])
	# Should print the Crumble recipe
	b.get_recipes_by_types("asdasd")
	# The recipe type does not exist, error must be handled in a justifiable manner
	# such as returning None, [], or printing an error message 
	```
    - With an correct type (with at least a recipe), the function must
      print all the recipes which match the type.
    - With a correct type which exists but being empty. This case must be handled properly
    - Verify also 'last_update' did not change
    - With a non existing recipe type, the function must declare an
      error and handle it correctly. Returning an empty array is also acceptable.

# Exercise 1: 'Exercise 01 - Family Tree'
## Description:
The goal of the exercise is to tackle the notion inheritance of class.

## Questions:
  - **Notion of class**\
    The exercise shows an example of inheritance of a class from a parent class.
    - Verify the implementation of the differents classes (GotCharacter and
      the children), parent should contains the attributes 'first_name' and
      'is_alive' while the children classes must have 'family_name',
      'house_words' and the 2 methods 'print_house_words' and 'die'
    - Verify when creating an instance of the GotCharacter class without any
      value that you get an object with the attributes 'first_name' sets to None
      and 'is_alive' sets to True.
    - Perform the same test and specify a value for the first_name and and
      is_alive, for example:
      `luigi = GotCharacter("Name", True)`
       Verify that the GotCharacter instance is alive and it's name.
    - Check the presence of the docstring  `print(luigi.\_\_doc\_\_)` (Some python setting can make this return None, if thats the case, go check in the code for an explanative text below `def GotCharacter():`)
     
    - Verify that the GotCharacter instance has no attributes 'house_words'
    or 'family_name' (of course you should not be able to call print_house_words()
    or the die() neither)
    
    - **children class**
      - Creates an instance of the children class and checks:
        `arya = Stark("Arya")`
      - Check the presence of the docstring
        `print(arya.\_\_doc\_\_)`
      - Verify all the attributes of the character
      - Verify that the methods associated to the character object
      - Use the method die() and verify the value of is_alive
      - Create a new instance with a different name, and verify it is alive
      and it name


# Exercise 2: 'Exercise 02 - The Vector'
## Description:
The goal of the exercise is to get you used with built-in methods,
more particularly with those allowing to perform operations.
Student is expected to code built-in methods for vector-vector and
vector-scalar operations as rigorously as possible.
Concerning the \_\_str\_\_ and \_\_repr\_\_ you have the opportunity to observe
their behaviors through the tests.

## Questions:
- **Implementation of built-in methods**\
  First, verifiy all the expected built-in methods are implemented, and
  then printing a vector you observe an output similar to:\
    ```(Vector [n1, ..., n2])```\
  You can note that clever implementation may used \_\_add\_\_ method within
  _radd_, \_\_sub\_\_ and \_\_rsub\_\_. Nethertheless it is perfectly fine if it is
  not the case.

- **built-in method \_\_init\_\_**   
  Verify the correct implementation of the \_\_init\_\_ method:
  Create multiple instances of Vector class according to the different
  possibilities and verify if the values and shape are correct:
  - ```python
    print(Vector([1. , 2e-3, 3.14, 5.]).values)
    # [1.0, 2e-3, 3.14, 5.0]
    ```

  - ```python
    print(Vector(4).values)
    # [[0.0], [1.0], [2.0], [3.0]]
    ```

  - ```python
    Vector(-1)
    # This is an error and should be properly handled by displaying an error message.
    ```
    
  - ```python
    print(Vector((10, 12)).values )
    # [[10.0], [11.0]]
    ```
  
  - ```python
    print(Vector((3, 1)).values)
    # Should display a properly handled error or [[3.0], [2.0]]
    ```

  - ``` python
    v = Vector((1, 1))
    print(v.values)
    # three behviours are acceptable
    # raise an error or print [] or print [[]]
    ```

  - ```python
    Vector((4, 7.1)) `:
    This is an error and should be properly handled by displaying an
    error message.
    ```


- **built-in methods \_\_mul\_\_ and \_\_rmul\_\_**  
  Verify the correct implementation of the built-in method \_\_mul\_\_ and
  \_\_rmul\_\_ by	performing several tests related to '*' operator:
    ```python
    v = Vector(4)
    print(v.values)
    # [[0.0], [1.0], [2.0], [3.0]]
    print(v * 4)
    # [[0.0], [4.0], [8.0], [12.0]]
    print(4.0 * v)
    # [[0.0], [4.0], [8.0], [12.0]]
    v * "hi"
    # The error should be handled, it should say raise SomeError in the code or print a message and return None or exit().
    ```

- **built-in method \_\_add\_\_, \_\_radd\_\_, \_\_sub\_\_ and \_\_rsub\_\_**\
  Verify the correct implementation of the built-in method \_\_add\_\_,
  \_\_radd\_\_, \_\_sub\_\_ and \_\_rsub\_\_ by performing several tests related
  to '+' and '-' operators:
  For each test verify that the result of the operation is a vector object or a scalar,
  and if it's value is correct.
  The following lines of code should output the same as the #comment below it
    ```python
    v = Vector(4)
    v2 = Vector([[1.0], [1.0], [1.0], [1.0]])
    print((v + v2).values)
    # [[1.0], [2.0], [3.0], [4.0]]

    v + Vector([0.0, 0.0, 0.0, 0.0])
    # The error shoudl be handled in some way

    v + "hello"
    # The error shoudl be handled in some way

    v + None
    # The error shoudl be handled in some way

    print((v - v2).values == (v2 -v).values)
    # True
    ```

- **built-in method \_\_div\_\_ and \_\_rdiv\_\_**\
  For division perform the following tests:
  - 'Vector(4) / 2'
  - 'Vector(4) / 3.14'
  - 'Vector(4) / 0'
    An error should be displayed, and properly handled.
  - 'Vector(4) / None' and 'None / Vector(4)'
    An error should be displayed, and properly handled
  - 3 / Vector(3) shoud raise an error or the choice of behaviour must be justifiable
    as multiple mathematical definitions of division by a vector exist.

# Exercise 3: 'Exercise 03 - Generator!'
## Description:
The goal of the exercise is to discover the concept of generator object
in Python, throught the implementation of a function 'generator' which
performs a splitting operation and an ordering class operation.

## Questions:
- **Error managament and basic tests**
  - First, check the implementation of the function (all behaviors are
  implemented: 'shuffle', 'ordered' and 'unique').
  - Verify the following cases are correctly managed and the message "ERROR"
  is printed:
    - Parameter 'text' is None
    - Parameter 'text' has a type different than 'str'
    - Parameter 'option' has a type different than 'str'
    - Parameter 'option' is specified and is a string different than 'unique',
      'ordered' and 'shuffle'

  - Secondly, with 'text' parameter being a string with multiple words and
    punctuation (for example text="This is a simple string for a basic test. Very simple."),
    runs the tests:
    ```
    for elem in my_generator:
      print(elem)
    ```
    With my_generator being:
      - `generator(txt, sep=' ')`
      - `generator(txt, sep='.')`
      - `generator(txt, sep='i')`
      - `generator(txt, sep='si')`
    For the given example the tests give (with line break between each strings):
    - First test: 'This' 'is' 'a' 'simple' 'string' 'for' 'a' 'basic' 'test.' 'Very' 'simple.'
    - Second test: 'This is a simple string for a basic test' ' Very simple' ''
    - Third test: 'Th' 's ' 's a s' 'mple str' 'ng for a bas' 'c test. Very s' 'mple.'
    - Fourth test: 'This is a ' 'mple strung for a ba' 'c test. Very ' 'mple.'

    - Finally, with 'text' parameter being a non empty string you must test
      'option' parameter. Check the value 'ordered' gives a alphanumerical
      ordering, 'unique' gives a set of the words (no identical strings) and
      'shuffle' randomly arrange the words. Spend a particular attention on
      the last value, 2 runs with 'shuffle' should not give the same
      arrangement (th opposite is highly unlikely). Verify also there is no missing words.


# Exercise 4: 'Exercise 04 - Working with lists'
## Description:
The goal of the exercise is to discover 2 useful methods for lists,
tuples, dictionnaries (iterable class objects more generally) named
zip and enumerate.

## Questions:
- **Error managament and basic tests**

  - First, check that the implementation of the class and methods.
    You must find 'zip' in the method 'zip_evaluate' and 'enumerate'
    in 'enumerate_evaluate' and no while loop. It is a normal implementation
    to find 'enumerate(zip(coefs, words))' so do not be surpised.
  - Verify the following cases are correctly managed and -1 is returned:
    - `Evaluator.enumerate_evaluate(None, None)`
    - `Evaluator.enumerate_evaluate([1, 2, 3], [])`
    - `Evaluator.enumerate_evaluate([1, 2, 3], ["word", 2, "wordo"])`

  - Then, test a few cases with lists length 1 and 2 to check the
    validity of the implementation and check no term of lists are missing
    in the sum of products (especially the last one).

# Exercise 5: 'Exercise 05 - Bank account'
## Description:
The goals of this exercise is to teach you new built-in functions and
get a deeper understanding about class manipulation and to be aware
of possibility to modify instanced objects.
In this exercise you learn how to modify or add attributes to an object.

## Questions:
  - **Error managament and basic tests**   
    - First, you have to check the classes implementation, meaning that you
      have to check the presence of:
      - the class Account and Bank in the file bank.py
      - the methods' \_\_init\_\_', 'transfer' and the attribute 'ID_COUNT' in
        the class Account.
      - the methods '\_\_init\_\_', 'add', 'transfer' and 'fix_account' in the
        class Bank.
        Student may have implement extra methods to manage the security
        aspect, thus it is okay to have more than the methods mentionned.

    - Second, you have to perform the following test to verify the security
      management:
      - `bank.add(account)`
        where 'bank' is an instance of Bank and 'account1' is a instance of
        Account which is considered as corrupted. Try several cases of corrupted
        account:
        ***if the Bank.add(account) funtion does not check for corrupted accounts simply verify that the function to check for corruption works***
        ```python
        from the_bank import Account, Bank

		bank = Bank()
		bank.add(Account(
		'William John',
		zip='100-064',
		brother="heyhey",
		value=6460.0,
		ref='58ba2b9954cd278eda8a84147ca73c87',
		info=None,
		other='This is the vice president of the corporation',
		lol = "hihi"
		))
		print(bank.account)
		# should print : []
		# the account is invalid because it has an attribute that starts with b

		bank = Bank()
		bank.add(Account(
		'William John',
		zip='100-064',
		rother="heyhey",
		value=6460.0,
		ref='58ba2b9954cd278eda8a84147ca73c87',
		info=None,
		other='This is the vice president of the corporation',
		))
		print(bank.account)
		# should print : []
		# the account is corrupted because it has an even number of attributes.


		bank = Bank()
		bank.add(Account(
			'William John',
			zip='100-064',
			rother="heyhey",
			ref='58ba2b9954cd278eda8a84147ca73c87',
			info=None,
			other='This is the vice president of the corporation',
			lol = "lolilol"
			))
		print(bank.account)
		# should print : []
		# the account is corrupted because it has no attribute "value".


		bank.add(Account(
			'Jane',
			zip='911-745',
			value=1000.0,
			ref='1044618427ff2782f0bbece0abd05f31'
			))
		jhon = Account(
			'Jhon',
			zip='911-745',
			value=1000.0,
			ref='1044618427ff2782f0bbece0abd05f31'
			)
		bank.add(jhon)

		print("\ntesting a valid transfer")
		print(jhon.value)
		# 1000.0

		bank.transfer("Jane", "Jhon", 500)
		print(jhon.value)
		# 1500.0

		print("\ntesting an invalid transfer")
		print(jhon.value)
		# 1500.0

		bank.transfer("Jane", "Jhon", 1000)
		print(jhon.value)
		# 1500.0
        ```