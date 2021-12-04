# Module 00 - Basics 1

## Comment:
This first module is the evolution of two original projects created by the Paris-based student organization 42 AI.
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

# Exercise 00 - $PATH
## Description:
The goal of the exercice is to understand how to set up a python environment and install some packages.

## Correction:
- Verify that the list of packages and its versions  correspond to those of the installed miniconda environment. To get the list of the pacakges and its versions run the following command:

  ```
  conda list
  ```

  Note that the version of a package and the version of Python evolved, thus do not refer to the latest version on conda website and pypi.org (or any other python package library).

- Verify that the content of the file answers.txt  corresponds to the return of the following command:

  <!---
  aulopez: pip search is being deprecated
  -->

  ```
  pip search tesseract -i https://pypi.org//pypi
  ```

- Verify that the content of the file answers.txt corresponds to the return of the following command:

  ```
  pip freeze > requirements.txt
  ```

# Exercise 01 - Rev Alpha
## Description:
The goal of the exercice is to manipulate string object functions.

The program take a string as an argument, reverses its order and cases, then print it. If multiple arguments are passed they must be joined together with a space.

## Correction:
Carry out at least the following test to stress the error management:
- Without argument:

  The program must do nothing or print an usage.

<!---
aulopez: using single quote instead of doublequote to avoid bad interpration of ! by bash terminal.
-->

- With a valid string:
  ```
  $> python3 exec.py 'Hello'
  Olleh
  ```

- With a string containing non alphabetical characters:
  ```
  $> python3 exec.py 'L337 5P3AK!'
  !ka3p5 733l
  ```

- With multiple arguments:
  ```
  $> python3 exec.py 'L337' '5P3AK!'
  !ka3p5 733l
  ```

- With multiple arguments including empty string. Verify the presence of the added space between each argument:

  ```
  python3 exec.py 'L337' '' '5P3AK!'
  !ka3p5  733l
  ```

# Exercise 02 - The Odd, the Even and the Zero
## Description:
The goal of the exercice is to manipulate integers with Python and perform some conditional tests based on modulo.

The program checks if a number is odd, even or zero.

## Correction:
Carry out at least the following test to stress the error management:

<!---
aulopez: adding example
-->

- Without argument:

  The program must do nothing or print an usage.

- With more than one argument:

  The program must report an error and quit.

  ```
  $> python3 whois.py 0 0
  ERROR
  ```

- With non integer parameters:

  The program must report an error and quit.

  ```
  $> python3 whois.py x
  ERROR
  ```

  ```
  $> python3 whois.py 1.5
  ERROR
  ```

- With a valid input:

  ```
  $> python3 whois.py 0
  I'm Zero.
  ```
  ```
  $> python3 whois.py 11
  I'm Odd.
  ```
  ```
  $> python3 whois.py 202
  I'm Even.
  ```

# Exercise 03 - Functional File
## Description:
The goal of the exercice is to work with built-in string functions and allows student to work with formatted strings.

<!---
aulopez: Errata probably needed: the subject does not seems to ask for an executable. Maybe add that to help the correction ?
  ```
  from sys import argv
  text_analyzer(*argv[1:])
  ```
--->

Note: if the program is not executable (ie. only contains a function), try adding this to the python file:
  ```
  from sys import argv
  text_analyzer(*argv[1:])
  ```

## Correction:
<!---
aulopez: adding tolerance for the format output
--->

Carry out at least the following test to stress the error management. Slight format difference are tolerated.

- Without argument:

  The program must take the input for the user and process it.

  ```
  $> python3 count.py
  [...]
  >> A very cool example !
  The text contains 15 character(s):
  - 1 upper letter(s)
  - 15 lower letter(s)
  - 1 punctuation mark(s)
  - 4 space(s)
  ```

- With more than one argument:

  The program must report an error and quit.
  ```
  $> python3 count.py 'Hello' 'World'
  ERROR
  ```

- With valid input:

  ```
  $> python3 count.py 'Another Example...'
  The text contains 13 character(s):
  - 2 upper letter(s)
  - 12 lower letter(s)
  - 3 punctuation mark(s)
  - 2 space(s)
  ```

- With an empty string:

  ```
  $> python3 count.py ''
  The text contains 0 character(s):
  - 0 upper letter(s)
  - 0 lower letter(s)
  - 0 punctuation mark(s)
  - 0 space(s)
  ```

# Exercise 04 - Elementary
## Description:
The goal of the exercice is to manipulate operator for numbers and allows student to work with string formatting.

The program prints the results of the four elementary mathematical operations of arithmetic (addition, substraction, multiplication, division) plus the modulo operation.

## Correction:
<!---
aulopez: the treatment of float requires an errata in the subject to avoid missintepretation
--->
Carry out at least the following test to stress the error management:

- Without 0, 1, 3 or more arguments:

  The program must report a descriptive error and display an usage.

- With valid inputs:

  ```
  $> python3 operations.py 21 42
  Sum:         63
  Difference:  -21
  Product:     882
  Quotient:    0.5
  Remainder:   21
  ```

- With the second parameter being 0:

  ```
  $> python3 operations.py 21 0
  Sum:         21
  Difference:  21
  Product:     0
  Quotient:    ERROR (div by zero)
  Remainder:   ERROR (modulo by zero)
  ```

- With invalid inputs:
  ```
  $> python3 operations.py 21 one
  [...]
  $> python3 operations.py 21 1e7
  [...]
  $> python3 operations.py 21 3.7
  [...]
  ```
  The program must report a descriptive error and display an usage.

# Exercise 05 - The right format
## Description:
The goal of the exercice is to discover tuple and dictionary object and also the formatted strings.

These program prints a formatted string from different data types.

## Correction:
Carry out at least the following test to stress the error management:

  ### Kata00
  The following tuple is expected in the file, which give the following output:
  ```
  t = (19,42,21)
  ...
  $> python3 kata00.py
  The 3 number(s) are: 19, 42, 21
  ```

  Modify the tuples with the expected following results:

  ```
  t = (1, 2, 3, 4) --> The 4 number(s) are: 1, 2, 3, 4
  t = ()           --> The 0 number(s) are:
  ```

  ### Kata01
  The following dictionary is expected in the file, which give the following output:
  ```
  languages = {
    'Python': 'Guido van Rossum',
    'Ruby': 'Yukihiro Matsumoto',
    'PHP': 'Rasmus Lerdorf',
    }
  ...
  $> python3 kata01.py
  Python was created by Guido van Rossum
  Ruby was created by Yukihiro Matsumoto
  PHP was created by Rasmus Lerdorf
  ```

  Modify the dictionary with the expected following results:

  ```
  languages = {} --> Nothing

  languages = {'A': 'B'} -->
  A was created by B

  languages = {'A': 'B', 'C': 'D'} -->
  A was created by B
  C was created by D
  ```

  ### Kata02
  <!---
  aulopez: errata required to forbid the use of datetime / strftime.
  The subject does not talk about the required spacing.
  --->
  The following tuple `(hour, minutes, year, month, day)` is expected in the file, which give the following output:
  ```
  t = (3, 30, 2019, 9, 25)
  ...
  $> python3 kata01.py
  09/25/2019 03:30
  ```

  Modify the tuple with the expected following results:
  ```
  t = (1, 1, 1, 1, 1)       --> 01/01/0001 01:01
  t = (10, 10, 100, 10, 10) --> 10/10/0100 10:10
  ```

  ### Kata03
  <!---
  aulopez: errata required for size above 42.
  --->
  The following string is expected in the file, which give the following result:
  ```
  phrase = "the right format"
  ...
  $> python3 kata03.py | cat -e
  --------------------------The right format%
  $> python3 kata03.py | wc -c
    42
  ```

  Modify the string with the expected following results. The result must be printed without an ending '\n' and the character count must be 42.

  Do not test string size above 42 characters.

  ```
  phrase = "hello"  --> -------------------------------------hello
  phrase = ""       --> ------------------------------------------
  phrase = "x" * 40 --> --xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
  ```

  ### Kata04
  <!---
  aulopez: errata required
  The subject does not talk about the required spacing.
  --->
  The following tuple is expceted in the file, which give the following result:
  ```
  t = (0, 4, 132.42222, 10000, 12345.67)
  ...
  $> python3 kata04.py | wc -c
  module_00, ex_04 : 132.42, 1.00e+04, 1.23e+04
  ```

  Modify the tuple with the expected following results:
  ```
  t = (1, 0, 1.0, 1, 1.0)           --> module_01, ex_00 : 1.00, 1.00e+00, 1.00e+00
  t = (15, 15, 15.155, 1554, 1.515) --> module_15, ex_15 : 15.15, 1.55e+03, 1.51e+00
  ```

# Exercise 06 - A recipe
## Description:
The goal of the exercice is to learn to work with a dictionary.

The program interactively manages cookbook recipes.

## Correction:
Carry out at least the following test to stress the error management:

 - Launch the program: a list of option and a prompt should be displayed:
 ```
 $> python3 recipe.py
 Please select an option by typing the corresponding number:
1: Add a recipe
2: Delete a recipe
3: Print a recipe
4: Print the cookbook
5: Quit
>>
 ```

- Try an option that does not exists:

  The program should display an error and ask for another prompt.

- Print the cookbook:

  The program should display a non-detailed list of Recipe

- Print an existing recipe:

  The program should display the recipe details.

- Print/delete a recipe that does not exists:

  The program should display an error and ask for another prompt.

- Add a recipe:

  You should be able to specify a name, ingredient lists, meal type and prep time. When you are finished, this recipe should appear in the cookbook and you should be able to print it.

- Delete all recipe > print the cookbook > add a recipe > print the cookbook:

  The program should not exit unexpectedly


# Exercise 07 - Shorter, faster, pythonest
## Description:
The goal of the exercice is to discover and work with list comprehension.

This program removes all the words in a string that are shorter than or equal to n letters, and returns the filtered list with no punctuation.

## Correction:
<!---
aulopez: accept None or empty list ?
--->
The program must use at least one list comprehension. In Python, list comprehension have the following form:
```
[operation(n) for n in array if condition(n)]
```

Carry out at least the following test to stress the error management:

- With 0, 1, 3 or more arguments:

  the program must declare an error and exit

- With valid inputs:

  ```
  $> python3 filterwords.py 'A BB CCC DD EEEE' 2
  ['CCC', 'EEEE']
  $> python3 filterwords.py 'EEEE' 2
  ['EEEE']
  $> python3 filterwords.py 'EEEE' 6
  [] or None
  ```

- With punctuations:
  ```
  $> python3 filterwords.py 'Hello, World!What a...lovely day' 4
  ['Hello', 'World', 'lovely']
  ```

- With an empty string:
  ```
  $> python3 filterwords.py '' 1
  [] or None
  ```

# Exercise 08 - S.O.S
## Description:
The goal of the exercice is to discover and work with list comprehension.

The program encode a string to Morse code and prints it. All alphanumeric characters must be handled. Other characters (except space) will cause the program to return an error and exit.

## Correction:
Carry out at least the following test to stress the error management:
- Without argument:

  The program does nothing

- With valid inputs:

  ```
  $> python3 sos.py "SOS"
  ... --- ...
  $> python3 sos.py "sos"
  ... --- ...
  $> python3 sos.py "42"
  ....- ..---
  $> python3 sos.py 'Hello World'
  .... . .-.. .-.. --- / .-- --- .-. .-.. -..
  $> python3 sos.py "a1 B2" "c3D4e5F6"
  .- .---- / -... ..--- / -.-. ...-- -.. ....- . ..... ..-. -....
  ```

- With non-alphanumeric character:

  ```
  $> python3 sos.py "#SOS"
  ERROR
  $> python3 sos.py 'Hello World!'
  ERROR
  ```

# Exercise 09 - Secret number
## Description:
The program is an interactive guessing game. It asks the user to guess a number between 1 and 99. The program will tell the user if their input is too high or too low. The game ends when the user finds out the secret number or type `exit`.

## Correction:
Carry out at least the following test to stress the error management:

<!---
aulopez: handling of decimal value must be clearer in the subject
--->
- Launch the program:

  It should print some text and ask for a user prompt:
  ```
  $> python3 guess.py
  This is an interactive guessing game!
  You have to enter a number between 1 and 99 to find out the secret number.
  Type 'exit' to end the game.
  Good luck!
  What's your guess between 1 and 99?
  >>
  ```

- Do a normal game:

  The program should declare a victory and print your attempt count.

- Use the exit command:

  The program should print "Goodbye!" and exit

- Use invalid input:

  - 'a'
  - [0]
  - hello...

  The program must not exit unexpectedly and ask for a new prompt.

- Use invalid number:
  - -1
  - 0
  - 100
  - 3.14
  - 1e7

  The program must not exit unexpectedly and ask for a new prompt. The attempt count might be affected.

# Exercise 10 - Loading bar!
## Description:
This exercice is a first contact with the notion of generator in Python.

Use the following test file if none is provided:
  ```
  from sys import argv
  from time import sleep
  from loading import ft_progress

  if len(argv) == 2:
    x = range(int(argv[1]))
  elif len(argv) == 3:
    x = range(int(argv[1]), int(argv[2]))
  else:
    x = range(int(argv[1]), int(argv[2]), int(argv[3]))
  ret = 0
  for elem in ft_progress(x):
    ret += elem
    sleep(0.01)
  print()
  print(ret)
  ```

## Correction:

The function must use the `yield` keyword.

Launching the test program should result in the display of a loading bar. Good job if the bar refresh in place !

```
$> python3 test.py 1000
[...]
ETA: 10.15s [ 37%][===========>                   ] 372/1000 | elapsed time 3.77s
[...]
```

Carry out at least the following tests. They should not produce any error and display a loading bar:
```
$> python3 test.py 100
$> python3 test.py 100 200
$> python3 test.py 1
$> python3 test.py 4
$> python3 test.py 0 -100 -1
```