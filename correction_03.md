# Module 03 - Numpy

## Comment:
This fourth module is the evolution of two original projects created by the
Paris-based student organization 42 AI.
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

## Introduction:
The Bootcamp Python and Bootcamp Machine Learning were originally created by
[42AI](https://github.com/42-AI) active members and were adapted to 'piscine'
format for the school 42 curriculum.
For any issue or suggestion: [42paris_staff_pedagogy](https://42born2code.slack.com/archives/C7NF60E0Z) and
[42AI](https://github.com/42-AI/bootcamp_python/issues).

As usual, you have to observe the following courtesy rules:

- Remain polite, courteous, respectful, and constructive throughout the evaluation process.
  The well-being of the community depends on it.

- Identify with the evaluated person or group the eventual dysfunctions of the assignment.
  Take the time to discuss and debate the problems you may have identified.

- You must consider that there might be some differences in the
  understanding of and approach to project instructions, and the scope of
  its functionalities, between you and your peers. Always remain open-minded
  and grade them as fairly as possible. The pedagogy is valid only and only
  if peer-evaluation is conducted seriously.

The goal of this module is to get started with the library Numpy.

## Disclaimer:
The serie of modules started to be produce at the time of the release of
Python 3.7. Students are free to use later version of Python as long as they
verified the producted code complies with all the aspects precised in the
subjects.
As a consequence we recommend to students to perform the modules with the
the Python version 3.7 (but this is just an advice).
Version can be checked with the command ```python -V```.

## Guidelines:
General rules
- Only grade the work that is in the student or group's GiT repository.

- Double-check that the GiT repository does belong to the student.
  Ensure that the work is the one expected for the corrected exercise
  and don't forget to verify that the command "git clone" is run in an empty folder.

- Check carefully that no malicious aliases were used to make
  you evaluate files that are not from the official repository.

- To avoid any surprises, carefully check that both the evaluating
  and the evaluated students have reviewed the possible scripts used to facilitate the grading.

- If the evaluating student has not completed that particular project yet,
  it is mandatory for them to read the entire subject prior to starting the defense.

- Use the flags available on this scale to signal an empty repository,
  non-functioning program, a Norm error (specified next in general rules), cheating, and so forth.
  In these cases, the grading is over and the final grade is 0,
  or -42 in case of cheating. However, except the exception of cheating, you
  are encouraged to continue to discuss your work even if the later is in
  progress in order to identify any issues that may have caused the project
  failure and avoid repeating the same mistake in the future.

- Use the appropriate flag.

- Remember that for the duration of the defense, no other unexpected,
  premature, or uncontrolled termination of the program, else the final grade is 0.

- You should never have to edit any file except the configuration file if
  the latter exists. If you want to edit a file, take the time to explain why
  with the evaluated student and make sure both of you agree on this.

- The Norm: You will follow the PEP 8 standards.

- The function eval is never allowed.

- Your exercises are going to be evaluated by other students,
  make sure that your variable names and function names are appropriate and civil.

# Exercise 0 NumPyCreator
### Guidelines:
To test this exercise, you can launch the follwing command on your terminal:
```bash
python
```
then
```bash
>>> from NumPyCreator import NumPyCreator
>>> npc = NumPyCreator()
>>>
```

### Basic tests
### Guidelines:
Check if all the following cases have a correct behaviour:
```python
>>> npc.from_list([[],[]])
array([], shape=(2, 0), dtype=float64)
>>> npc.from_list([[1,2,3],[6,3,4],[8,5,6]])
array([[1, 2, 3],
       [6, 3, 4],
       [8, 5, 6]])
>>> npc.from_tuple(("a","b","c"))
array(['a', 'b', 'c'], dtype='<U1')
>>> npc.from_iterable(range(5))
array([0, 1, 2, 3, 4])
>>> npc.from_shape((0, 0))
array([], shape=(0, 0), dtype=float64)
>>> npc.from_shape((3, 5))
array([[0., 0., 0., 0., 0.],
       [0., 0., 0., 0., 0.],
       [0., 0., 0., 0., 0.]])
>>> npc.random((3, 5))
array([[0.74819604, 0.32295616, 0.27371925, 0.57171326, 0.92582071],
       [0.70307642, 0.94846695, 0.12465384, 0.25146454, 0.11179953],
       [0.38326719, 0.26179493, 0.88157011, 0.29978869, 0.72677049]])
>>> npc.identity(4)
array([[1., 0., 0., 0.],
       [0., 1., 0., 0.],
       [0., 0., 1., 0.],
       [0., 0., 0., 1.]])
```


### Error management
The different methods should handle wrong type, ragged nested list/tuple.
Perform at least the following cases, they should all return None:
```python
print(npc.from_list("toto"))
print(npc.from_list([[1,2,3],[6,3,4],[8,5,6,7]]))
print(npc.from_tuple(3.2))
print(npc.from_tuple(((1,5,8),(7,5))))
print(npc.from_shape((-1, -1)))
print(npc.identity(-1))
```


# Exercise 1 ImageProcessor
## Implementation
### Guidelines:
To test this exercise, you can launch the follwing command on your terminal:
```bash
python
```
then
```bash
>>> from ImageProcessor import ImageProcessor
>>> imp = ImageProcessor()
>>>
```
Verify the class ImageProcessor and that the methods 'load' and 'display'
are implemented.

As a class, special method '\_\_init\_\_' has to be present.
- The method 'load' handles empty and non existing file.
```python
>>> arr = imp.load("../ressources/42AI.png")
Loading image of dimensions 200 x 200
>>> print(arr)
```
The print should display a nested list of RGB pixel numbers contained by the image (cf subject)
- The method 'display' handles non array-like, empty or None argument.
```python
>>> imp.display(arr)
```
The image should be displayed in a separate window when running in the console.

    
# Exercise 2 ScrapBooker
## Basic tests
### Guidelines:
Perform basic tests to verify the proper behaviour of the different methods.
```python
>>> import numpy as np
>>> from ScrapBooker import ScrapBooker
>>> spb = ScrapBooker()
>>> arr1 = np.arange(0,25).reshape(5,5)
>>> spb.crop(arr1, (3,1),(1,0))
array([[ 5],
       [10],
       [15]])
>>> arr2 = np.array("A B C D E F G H I".split() * 6).reshape(-1,9)
>>> spb.thin(arr2,3,0)
array([['A', 'B', 'D', 'E', 'G', 'H'],
       ['A', 'B', 'D', 'E', 'G', 'H'],
       ['A', 'B', 'D', 'E', 'G', 'H'],
       ['A', 'B', 'D', 'E', 'G', 'H'],
       ['A', 'B', 'D', 'E', 'G', 'H'],
       ['A', 'B', 'D', 'E', 'G', 'H']], dtype='<U1')
>>> arr3 = np.array([[var] * 10 for var in "ABCDEFG"])
>>> spb.thin(arr3,3,1)
array([['A', 'A', 'A', 'A', 'A', 'A', 'A', 'A', 'A', 'A'],
       ['B', 'B', 'B', 'B', 'B', 'B', 'B', 'B', 'B', 'B'],
       ['D', 'D', 'D', 'D', 'D', 'D', 'D', 'D', 'D', 'D'],
       ['E', 'E', 'E', 'E', 'E', 'E', 'E', 'E', 'E', 'E'],
       ['G', 'G', 'G', 'G', 'G', 'G', 'G', 'G', 'G', 'G'],
       ['H', 'H', 'H', 'H', 'H', 'H', 'H', 'H', 'H', 'H'],
       ['J', 'J', 'J', 'J', 'J', 'J', 'J', 'J', 'J', 'J'],
       ['K', 'K', 'K', 'K', 'K', 'K', 'K', 'K', 'K', 'K']], dtype='<U1')
>>> arr4 = np.array([[1, 2, 3],[4, 5, 6],[7, 8, 9]])
>>> spb.juxtapose(arr4, 2, 0)
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9],
       [1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])
```

## Error managment
### Guidelines:
First, verify the class is correctly implemented and has the 4 methods and the
constructor ('\_\_init\_\_').

Verify the different methods handles incorrect parameters:
- Non numpy.array for arr parameter. The functions return None.
- dim different than a tuple of 2 acceptable integers for 'crop' and 'mosaic'. The functions return None.
- position being different than (int1, int2) for 'crop'. The function returns None.
- axis parameter for 'thin' and 'juxtapose' different than 0 and 1. The functions return None.
      
Verify the other combinaison of incorrect parameters.


# Exercise 3 ColorFilter
## Error managment
### Guidelines:
First, verify the 6 methods plus the constructr are implemented in the class
'ColorFilter'.

As usual, check the error managment of the different methods.


## Basic tests
### Guidelines:
Test the different methods, by taking a picture of your choice and applying the filters.
try this on your terminal for example:
```python
>>> import numpy as np
>>> import matplotlib
>>> from matplotlib import pyplot as plt
>>> from ColorFilter import ColorFilter
>>> cf = ColorFilter()
>>> array = plt.imread("<path_to_png_file>")
>>> green = cf.to_green(array)
>>> plt.imshow(green)
>>> plt.show()
```
You should observed the 'to_green' method generate a new array corresponding to the original image with a green filter, and so on.

# Exercise 4 K-means Clustering
## Implementaion & Basic tests
### Guidelines:
- First verify the correct implementation of the class (constructor and methods).
- The centroids are randomly initialized.
- Program can handles different set of values (reasonnable ones) for 'ncentroid' and 'max_iter' arguments.
- For a fix value of 'ncentroid', centroids coordinates slightly differ when running the algorithm multiple times.
- Results are coherent and consistent trough multiple program execution.
  Most of the time, centroids converged to similar coordinates and number people associated to each centroids varies little.
