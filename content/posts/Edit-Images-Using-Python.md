---
title: "Edit Images Using Python"
date: 2022-12-18T19:07:18+01:00
tags: ['python','python3', 'image-editing', 'coding']
draft: true
toc: true
---

# Edit Images Using Python

There's plenty of image editing software out there, most notably Photoshop - 
but did you know you can also edit images using Python? 
While Pillow, the Python library used in this tutorial, won't replace Photoshop,
it does help you to perform certain actions faster - and completely free.
<!-- List things we'l cover in this tut -->

## Import Pillow library

Use `pip install` command.

## First steps in  Pillow: convert image format

1. Import `Image` class to create an Image object 
This module contains an Image class  
    The Image module provides a class with the same name which is used to represent a PIL image.
    See docs
```python
import Image
```

2. Open a jpeg image:
```python
img = Image.open('img1.jpg')
```

3. Save as a png image:

```python
im.save('img1.png')
```

## Play with Image Filters

Pillow comes with some pre-defined filters so you can play around with those without much hassle. 
These filters include: 
- BLUR
- EMBOSS
- FIND_EDGES
- SHARPEN

1. Import ImageFilter module. 
2. 


Using one of these filters allows you to get the results quickly, without having to play around with the parameters.
 
### Gaussian blur

You can achieve more sophisticated results using custom filters. 
Gaussian blur filter allows you to add parameters for the radius, so deepending on the desired result,
you can choose to make the image extremely blurry or only ever so-slightly.



```python
edit = img.filter(ImageFilter.GaussianBlur(radius=25))
```

## Enhance your images

Import ImageEnhance 

```python
contrast_enhancer = ImageEnhance.Contrast(image) 
brightness_enhancer = ImageEnhance.Brightness(image) 
sharpness_enhancer = ImageEnhance.Sharpness(image) 
```

My full snippet

```python
from PIL import Image, ImageEnhance, ImageFilter, ImageColor
import os

# Define path to and from img folder
path = './imgs'
pathOut = '/maxEnhance'

for filename in os.listdir(path):
    img = Image.open(f"{path}/{filename}")
    edit = img.filter(ImageFilter.GaussianBlur(radius=25))
    color_enhancer = ImageEnhance.Color(edit)
    contrast_enhancer = ImageEnhance.Contrast(edit)
    brightness_enhancer = ImageEnhance.Brightness(edit)
    edit = color_enhancer.enhance(5)
    edit = brightness_enhancer.enhance(2)
    edit = contrast_enhancer.enhance(5)
    clean_name = os.path.splitext(filename)[0]

    edit.save(f'.{pathOut}/{clean_name}_max.jpg')
```