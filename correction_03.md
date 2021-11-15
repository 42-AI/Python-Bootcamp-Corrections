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
python3
```
then
```python
from NumPyCreator import NumPyCreator
npc = NumPyCreator()
```

## Basic tests
In this python interpretor, check if all the following cases have a correct behaviour:

- This command:
  ```python
  npc.from_list([[],[]])
  ```
  Shoud Output:
  ```
  array([], shape=(2, 0), dtype=float64)
  ```
<br>

- This command:
  ```python
  npc.from_list([[1,2,3],[6,3,4],[8,5,6]])
  ```
  Shoud Output:
  ```
  array([[1, 2, 3],
        [6, 3, 4],
        [8, 5, 6]])
  ```
<br>

- This command:

  ```python
  npc.from_tuple(("a","b","c"))
  ```
  Shoud Output:
  ```
  array(['a', 'b', 'c'], dtype='<U1')
  ```

<br>

- This command:
  ```python
  npc.from_iterable(range(5))
  ```
  Shoud Output:
  ```
  array([0, 1, 2, 3, 4])
  ```

<br>

- This command:
  ```python
  npc.from_shape((0, 0))
  ```
  Shoud Output:
  ```
  array([], shape=(0, 0), dtype=float64)
  ```

<br>

- This command:
  ```python
  npc.from_shape((3, 5))
  ```
  Should output:
  ```
  array([[0., 0., 0., 0., 0.],
        [0., 0., 0., 0., 0.],
        [0., 0., 0., 0., 0.]])
  ```
<br>

- This command:
  ```python
  npc.random((3, 5))
  ```
  Should output (*the values are random but th shape must be the same)*:   
  ```
  array([[0.74819604, 0.32295616, 0.27371925, 0.57171326, 0.92582071],
        [0.70307642, 0.94846695, 0.12465384, 0.25146454, 0.11179953],
        [0.38326719, 0.26179493, 0.88157011, 0.29978869, 0.72677049]])`
  ```

<br>

- This command:
  ```python
  npc.identity(4)
  ```
    Should output:   
  ```
  array([[1., 0., 0., 0.],
        [0., 1., 0., 0.],
        [0., 0., 1., 0.],
        [0., 0., 0., 1.]])
  ```


For values contained in identity and from_shape function, both integer and float values are acceptable.


## Error management
Run this:
```python
print(npc.from_list("toto"))
print(npc.from_list([[1,2,3],[6,3,4],[8,5,6,7]]))
print(npc.from_tuple(3.2))
print(npc.from_tuple(((1,5,8),(7,5))))
print(npc.from_shape((-1, -1)))
print(npc.identity(-1))
```
Should print:
```python
None
None
None
None
None
None
```

# Exercise 1 ImageProcessor
## Implementation
### Guidelines:
To test this exercise, you can launch the follwing command on your terminal:
```bash
python3
```

then
```bash
from ImageProcessor import ImageProcessor
imp = ImageProcessor()
```

Verify the class ImageProcessor and that the methods '**load**' and '**display**'
are implemented in \"ImageProcessor.py\".

As a class, special method '**\_\_init\_\_**' has to be present.
- The method '**load** :
  ```python
  arr = imp.load("../ressources/42AI.png")
  # Loading image of dimensions 200 x 200
  print(arr)
  ```
  The print should display a nested list of RGB pixel numbers contained by the image (cf subject)

<br>

- The method '**display**' :.
  ```python
  imp.display(arr)
  ```
  The image should be displayed in a separate window when running in the console.

<br>
<br>
    
# Exercise 2 ScrapBooker
## Basic tests
Perform basic tests to verify the proper behaviour of the different methods.
First, launch the python interpreter by taping the following command on your terminal:
```
python3
```
- then copy paste the commands and check if they have the same output aviour as here:
  ```python
  import numpy as np
  from ScrapBooker import ScrapBooker
  spb = ScrapBooker()
  arr1 = np.arange(0,25).reshape(5,5)
  spb.crop(arr1, (3,1),(1,0))
  ```

  Output:
  ```python
  array([[ 5],
        [10],
        [15]])
  ```

<br>

-
  ```python
  arr2 = np.array("A B C D E F G H I".split() * 6).reshape(-1,9)
  spb.thin(arr2,3,0)
  ```
  
  Output :  
  ```python
  array([['A', 'B', 'D', 'E', 'G', 'H'],
        ['A', 'B', 'D', 'E', 'G', 'H'],
        ['A', 'B', 'D', 'E', 'G', 'H'],
        ['A', 'B', 'D', 'E', 'G', 'H'],
        ['A', 'B', 'D', 'E', 'G', 'H'],
        ['A', 'B', 'D', 'E', 'G', 'H']], dtype='<U1')
  ```

<br>

-
  ```python
  arr3 = np.array([[var] * 10 for var in "ABCDEFG"])
  spb.thin(arr3,3,1)
  ```

  Output :  
  ```python
  array([['A', 'A', 'A', 'A', 'A', 'A', 'A', 'A', 'A', 'A'],
        ['B', 'B', 'B', 'B', 'B', 'B', 'B', 'B', 'B', 'B'],
        ['D', 'D', 'D', 'D', 'D', 'D', 'D', 'D', 'D', 'D'],
        ['E', 'E', 'E', 'E', 'E', 'E', 'E', 'E', 'E', 'E'],
        ['G', 'G', 'G', 'G', 'G', 'G', 'G', 'G', 'G', 'G']], dtype='<U1')
  ```

<br>

-
  ```python
  arr4 = np.array([[1, 2, 3],[4, 5, 6],[7, 8, 9]])
  spb.juxtapose(arr4, 2, 0)
  ```

  Output :
  ```python
  array([[1, 2, 3],
        [4, 5, 6],
        [7, 8, 9],
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]])
  ```

## Error managment
First, verify the class is correctly implemented and has the 4 methods and the
constructor ('\_\_init\_\_').
try:
```python
not_numpy_arr = [[1, 2, 3],[4, 5, 6],[7, 8, 9]]
spb.crop(not_numpy_arr, (1,2))
spb.juxtapose(arr4, -2, 0)
spb.mosaic(arr4, (1, 2, 3))
```
These functions should all return None because of incorect parameters (*Nothing will show on screen when you run the above code*)

<br>
<br>


# Exercise 3 ColorFilter

## Basic tests
Test the different methods, by taking a .png image of your choice and applying the filters.   
**The defendee may run ANY code he wishes to show the image effects to validate this excercise. This code is only meant to facilitate correction.**  
Celluloid is poorly documented so it is considered optional. 

<br>

Copy this code into a file, replace `"<PATH_TO_THE_IMAGE>"` by the actual path to the image and run the file with python (if the image is not a true .png this will crash, run it with the elonGAN image).
```python
import numpy as np
import matplotlib
from matplotlib import pyplot as plt

from ColorFilter import ColorFilter
cf = ColorFilter()

for f in [cf.to_red, cf.to_green, cf.to_blue, cf.invert]:
	array = plt.imread("<PATH_TO_THE_IMAGE>")
	plt.imshow(f(array))
	plt.show()

im = cf.to_grayscale(array, "m")
plt.imshow(im, cmap="gray")
plt.show()

im = cf.to_grayscale(array, "w", weights = [0.2126, 0.7152, 0.0722])
plt.imshow(im, cmap="gray")
plt.show()
```

You should see a Red, Blue, Green, Inverted and Gray version of the image   
**YOU HAVE TO CLOSE THE IMAGES THAT SHOW ON SCREEN FOR THE NEXT IMAGE TO SHOW**   

<br>
<br>

# Exercise 4 K-means Clustering
## Implementaion & Basic tests
### Guidelines:
- First verify the correct implementation of the class (constructor and methods).
  Try launching the following command with the corresponding path on your terminal:
  ```bash
  python Kmeans.py filepath='<path_to_solar_system_census_csv_file>' ncentroid=4 max_iter=30
  ```
- The centroids are randomly initialized.
- Program can handles different set of values (reasonnable ones) for 'ncentroid' and 'max_iter' arguments.
- For a fix value of 'ncentroid', centroids coordinates slightly differ when running the algorithm multiple times.
- Results are coherent and consistent trough multiple program execution.
  Most of the time, centroids converged to similar coordinates and number people associated to each centroids varies little.
