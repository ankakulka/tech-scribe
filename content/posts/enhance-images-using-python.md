---
title: "Enhance Images Using Python"
date: 2023-01-02T15:05:35+01:00
draft: true
toc: true
---

### Play with Image Filters

Pillow comes with some pre-defined filters so you can play around with those without much hassle. 
These filters include: 
- BLUR
- EMBOSS
- FIND_EDGES
- SHARPEN

1. Import ImageFilter module. 



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