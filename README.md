# CSCI_4120_HW3

Name: Naomi Jainarine Email: jainarinen20@students.ecu.edu

Name: Pusp Raj Bhatt Email: bhattp20@students.ecu.edu

# Exc 1 

Before you begin, you want to down load the packages below and import the data using the following code:

```
%pylab inline
# %pylab magic function is entered at the IPython prompt, it triggers the import of various modules within Matplotlib
from scipy import *
from numpy.linalg import norm
from math import sqrt,sin,cos
import pandas as pd
import numpy as np
from numpy import arange,array,ones,linalg
```

```
HW=pd.read_csv('data/gauss_R2.csv')
```
When adding a 'y-x' column to the data frame using a def function, you must place your code in the "return" section of the code to cause an "in-line" change in the data frame. If you misplace your code in the def function, your data frame will not be changed and your column will not be saved. Use the code below and then run the "self-check" cell to generate image 1. 

```
def y_minus_x(HW):
  
    HW['y-x']= HW.y-HW.x

print (y_minus_x(HW))
print (HW.shape)
print (HW.columns)
HW.head()
```
![Image 1](https://github.com/jainarinen/CSCI_4120_HW3/blob/main/hw3_image1.JPG)


#Exc 2

To generate the second figure, you must use the linalg function. Your data frame should be converted to a numpy array (for the output). The ones () function will allow you to merge a column of ones with with x, similar to the vstack() function. The linalg function has a variable "rcond=none" that can be used to round small values to 0. The final code is pictured below.

```def do_regression(HW):
    # input: the HW's dataset
    # output: a numpy array yielding w=(w0,w1) from linear regression
    
    # Your code
    # vstack merges a column containing only ones with x
    
    return linalg.lstsq(np.array([ones(HW.shape[0]),HW.x]).T,HW['y-x'],rcond=-1)[0]
   
    ```
    
    After you run this code, run the self-check cell. This will generate the figure below.
![Image 2](https://github.com/jainarinen/CSCI_4120_HW3/blob/main/hw3_image2.JPG)
