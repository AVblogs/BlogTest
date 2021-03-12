---
layout: post
title: Inert(ia)
---

##### Inception

It's been a year since **COVID** hit, and we've been stuck in this fugue state of lockdown and little to no personal contact. a great way of coping with this is to regress even further on the internet to eventully be one with the web, this blog is my first step in achieving the 'skynet dream'. 


##### Content 

I don't know if you're familiar with much of Shakespeare's work, but if I were to ascribe a title of one of his plays to describe this blog, it'd be 'much ado about nothing'. Don't expect anything else other than, poorly written, insane stream of consciousness babbling.

To get the ball rolling: let's start with with a wee bit of code, which allows us to cary our some simple 'band math' while using google colab
``` python 
import gdal
!pip install rasterio
import rasterio
from google.colab import drive
drive.mount('/content/drive')

myDir = '/content/drive/My Drive/Python files/'

import os
if os.path.exists(myDir + 'sfu.tif'):
  print("Drive mounted and directory found")
else:
  print("No access to the files")
  
filename = myDir + 'sfu.tif'
ds = rasterio.open(filename) #ds is just shorthand for 'data set'

print("Dataset name is", ds.name)
print("Number of bands in dataset", ds.count)
print("Number of columns in dataset", ds.width)
print("Number of rows in dataset", ds.height)

import numpy as np
band1 = ds.read(1)
band2 = ds.read(2)
band3 = ds.read(3)
brightness = (band1 + band2 + band3) / 3
brightness


'''



