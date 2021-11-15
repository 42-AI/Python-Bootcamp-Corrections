# Module 04 - Pandas

## Comment:
This fifth module is the evolution of two original projects created by the
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

- You must consider that there might be some differences in the understanding
  of and approach to project instructions, and the scope of its functionalities,
  between you and your peers. Always remain open-minded and grade them as fairly as possible.
  The pedagogy is valid only and only if peer-evaluation is conducted seriously.

The goal of this module is to get started with the library Pandas and the
manipulation of dataframes.

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

- Use the flags available on this scale to signal an empty repository, non-functioning program,
  a Norm error (specified next in general rules), cheating, and so forth.
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

# Exercise 0 - FileLoader
The goal of this exercise is to create a Fileloader class containing a load and a display method.   
    
put the csv file in the current directory
```python
from FileLoader import FileLoader

f = FileLoader()

df = f.load("./athlete_events.csv")
# (271116, 15) displays the size of loaded dataset
f.display(df, 3)
#    ID                 Name Sex   Age  Height  Weight     Team  NOC        Games  Year  Season       City       Sport                         Event Medal
# 0   1            A Dijiang   M  24.0   180.0    80.0    China  CHN  1992 Summer  1992  Summer  Barcelona  Basketball   Basketball Men's Basketball   NaN
# 1   2             A Lamusi   M  23.0   170.0    60.0    China  CHN  2012 Summer  2012  Summer     London        Judo  Judo Men's Extra-Lightweight   NaN
# 2   3  Gunnar Nielsen Aaby   M  24.0     NaN     NaN  Denmark  DEN  1920 Summer  1920  Summer  Antwerpen    Football       Football Men's Football   NaN
print("\n\n")
f.display(df, -3)
# ID                Name Sex   Age  Height  Weight    Team  NOC        Games  Year  Season            City        Sport                               Event Medal
# 271113  135570            Piotr ya   M  27.0   176.0    59.0  Poland  POL  2014 Winter  2014  Winter           Sochi  Ski Jumping  Ski Jumping Men's Large Hill, Team   NaN
# 271114  135571  Tomasz Ireneusz ya   M  30.0   185.0    96.0  Poland  POL  1998 Winter  1998  Winter          Nagano    Bobsleigh                Bobsleigh Men's Four   NaN
# 271115  135571  Tomasz Ireneusz ya   M  34.0   185.0    96.0  Poland  POL  2002 Winter  2002  Winter  Salt Lake City    Bobsleigh                Bobsleigh Men's Four   NaN
print("\n\n")

f.display(df, 0)
# should display Nothing or the Header (column names of the)

f.display(df, "lol")
#shouldnt crash

```

## Load and display methods tests'
Check if load method works correctly with a valid path:
- returns a pandas.DataFrame object
- displays the number of rows and columns loaded in the DataFrame,
  for the 'athlete_events.csv' 271116 rows and 14 columns.

# Exercise 1 - YoungestFellah
The goal of this exercise is to create a function that will return a
dictionary containing the age of the youngest woman and the youngest
man who took part in the Olympics a given year.
    
## Basic tests'
Check the results of the following cases:
(Please adatp the file path in the load function)
```python
from FileLoader import FileLoader
from YoungestFellah import youngestfellah
loader = FileLoader()
data = loader.load('<PATH_TO_CSV_FILE>')
```

- "youngestfellah(data, 1992)", output is: "{'f': 12.0, 'm': 11.0}"
- "youngestfellah(data, 2004)", output is: "{'f': 13.0, 'm': 14.0}"
- "youngestfellah(data, 2010)", output is: "{'f': 15.0, 'm': 15.0}"
- "youngestfellah(data, 2003)", output is: "{'f': nan, 'm': nan}"

Odd years, years before 1952 and after 2008 must return nan for both gender or a similar result.
If something does not match, the exercise is failed. 

<br>
<br>

# Exercise 2 - ProportionBySport
The goal of this exercise is to create a function displaying the proportion
of participants who played a given sport, among the participants of a given
genders.
    
## Basic tests'
Verify the results of the following cases: (please adapt the path to csv file)
```python
from FileLoader import FileLoader
from ProportionBySport import proportionBySport
loader = FileLoader()
data = loader.load('<PATH_TO_CSV_FILE>')
```
- "proportionBySport(data, 2004, 'Tennis', 'F')" , output is "0.02307"
- "proportionBySport(data, 2008, 'Hockey', 'F')", output is  "0.03284"
- "proportionBySport(data, 1964, 'Biathlon', 'M')", output is "0.00659"

**The rounding of the result does no matter (0.023 or 0.02307969707897584 or 2.3 % are all acceptable**   
If something does not match, the exercise is failed.

<br>
<br>

# Exercise 3 - HowManyMedals
The goal of this exercise is to code a function that will return
a dictionary of dictionaries giving the number and type of medals
for each year during which the participant won medals.
    
## Basic tests
Verify the results of the following cases: (Please adapt the path to csv file)
```python
import pandas as pd
from HowManyMedals import howManyMedals
data = pd.read_csv('<PATH_TO_CSV_FILE>')
```
- "howManyMedals(data, 'Gary Abraham')",
  the output is: "{1976: {'G': 0, 'S': 0, 'B': 0}, 1980: {'G': 0, 'S': 0, 'B': 1}}"
- "howManyMedals(data, 'Yekaterina Konstantinovna Abramova')",
  the output is "{2006: {'G': 0, 'S': 0, 'B': 1}, 2010: {'G': 0, 'S': 0, 'B': 0}}"
- "howManyMedals(data, 'Kristin Otto')",
  the output is: "{1988: {'G': 6, 'S': 0, 'B': 0}}"

If something does not match, the exercise is failed. 

<br>
<br>


# Exercise 4 - SpatioTemporalData
The goal of this exercise is to write a class called SpatioTemporalData
that takes a dataset (pandas.DataFrame) as argument in its constructor
and implements two methods.
    

## Basic tests
Check the result of the following cases: (please adapt path to csv file)
```python
import pandas as pd
from SpationTemporalData import SpatioTemporalData
df = pd.read_csv('<PATH_TO_CSV_FILE>)
sp = SpatioTemporalData(df)
```
- "print(sp.where(2000))", output is: "['Sydney']"
- "print(sp.where(1980))", output is: "['Lake Placid', 'Moskva']" If a single of these locations is returned it's ok.
- "print(sp.when('London'))", output is: "[2012, 1948, 1908]"

You should try other locations and years. 
If something does not match, the exercise is failed.


# Exercise 5 - HowManyMedalsByCountry
The goal of this exercise is to write a function that returns a
dictionary of dictionaries giving the number and type of medal for
each competition where the country delegation earned medals.


## Basic tests'
Print the result of howManyMedalsByCountry functions calls with various countries
and check that the format respects the following:
```python
import pandas as pd
from HowManyMedalsByCountry import howManyMedalsByCountry
data = pd.read_csv("PATH_TO_ATHLETES_CSV")
print(howManyMedalsByCountry(data, "United States") == {1896: {'G': 11, 'S': 7, 'B': 2}, 1900: {'G': 18, 'S': 14, 'B': 13}, 1904: {'G': 64, 'S': 67, 'B': 65}, 1906: {'G': 12, 'S': 6, 'B': 6}, 1908: {'G': 34, 'S': 16, 'B': 15}, 1912: {'G': 46, 'S': 25, 'B': 36}, 1920: {'G': 84, 'S': 41, 'B': 35}, 1924: {'G': 63, 'S': 40, 'B': 35}, 1928: {'G': 37, 'S': 21, 'B': 17}, 1932: {'G': 58, 'S': 56, 'B': 43}, 1936: {'G': 30, 'S': 29, 'B': 27}, 1948: {'G': 56, 'S': 34, 'B': 29}, 1952: {'G': 53, 'S': 38, 'B': 24}, 1956: {'G': 37, 'S': 55, 'B': 20}, 1960: {'G': 82, 'S': 27, 'B': 18}, 1964: {'G': 74, 'S': 35, 'B': 27}, 1968: {'G': 85, 'S': 35, 'B': 34}, 1972: {'G': 69, 'S': 58, 'B': 31}, 1976: {'G': 62, 'S': 41, 'B': 28}, 1980: {'G': 24, 'S': 4, 'B': 2}, 1984: {'G': 134, 'S': 68, 'B': 32}, 1988: {'G': 64, 'S': 43, 'B': 33}, 1992: {'G': 77, 'S': 39, 'B': 47}, 1994: {'G': 6, 'S': 8, 'B': 5}, 1996: {'G': 97, 'S': 38, 'B': 25}, 1998: {'G': 25, 'S': 2, 'B': 3}, 2000: {'G': 67, 'S': 29, 'B': 45}, 2002: {'G': 9, 'S': 52, 'B': 9}, 2004: {'G': 63, 'S': 64, 'B': 36}, 2006: {'G': 9, 'S': 7, 'B': 32}, 2008: {'G': 59, 'S': 58, 'B': 47}, 2010: {'G': 8, 'S': 61, 'B': 20}, 2012: {'G': 80, 'S': 44, 'B': 36}, 2014: {'G': 8, 'S': 28, 'B': 16}, 2016: {'G': 92, 'S': 51, 'B': 43}})
```
Should output `True`
**If the previous test fails the defendee should use the following list for team sports**, If he does not filter for team sports, he failed the exercise.   
```python
team_sports = ['Basketball', 'Football',  'Tug-Of-War', 'Badminton', 'Sailing', 'Handball', 'Water Polo', 'Hockey', 'Rowing', 'Bobsleigh', 'Softball', 'Volleyball', 'Synchronized Swimming', 'Baseball', 'Rugby Sevens', 'Rugby', 'Lacrosse', 'Polo']
```

# Exercise 6 - MyPlotLib
The goal the exercise is to introduce plotting methods among the different
libraries Pandas, Matplotlib, Seaborn or Scipy
    

## Basic tests'
Performs the following basic tests with the given dataset
with at least 3 numerical features:
- run the method histogram with one, two and three valid features
- run the method density with one, two and three valid features
- run the method pair_plot with one, two and three valid features
- run the method box_plot with one, two and three valid features

# Exercise 7 - Komparator
The goal the exercise is to introduce plotting methods among the different
libraries Pandas, Matplotlib, Seaborn or Scipy.
    

## Basic tests'
Verify you get the expected plots for each methods:
-
- giving 'Medal' and 'Age' for the method compare_box_plots, you
  should observe 3 boxes: Bronze. Silver and Gold
- giving 'Medal' and 'Height' for the method compare_histograms, you
  should observe 3 histograms
- giving 'Medal' and 'Weight' for the method density, you should
  observe 3 curves of density plot
