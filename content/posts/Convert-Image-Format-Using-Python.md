---
title: "Convert image format using Python"
date: 2022-12-18T19:07:18+01:00
tags: ['python','python3', 'beginner-python', 'image-editing', 'coding']
draft: false
toc: true
omit_header_text: true
summary: "How to guide for users with basic familiarity of Python"
---


There's plenty of image editing software out there, most notably Photoshop - 
but did you know you can also edit images using Python? 
While [Pillow](https://pillow.readthedocs.io/en/stable/index.html#), the Python library used in this tutorial, won't replace Photoshop,
it does help you to perform certain actions **faster** - and completely free.

In this introductory tutorial I'll show you how to convert image format using Pillow library.
You can then build on that knowledge to progress to the more advanced concepts, such as Image filters. 

I'm using Python version 3. 

> **Tip!** Some basic Python knowldege required!

### Install Pillow

First, we need to prepare our paints and brushes, in our case it means installing the Pillow library. <br/>

In your terminal type:
```bash
pip install Pillow
```

### Convert image format 

Converting the image format in the Pillow library is quick and easy.
In this example I'll show you how to convert a **JPEG** image to a **PNG**.

You can also use Pillow to convert to and from other popular image formats such as:
- BMP
- GIF
- EPS
- TIFF

Check out the docs for the [full list of supported formats](https://pillow.readthedocs.io/en/stable/handbook/image-file-formats.html).  

1. In your Python file, import `Image` from the Pillow library. 
The `Image` module contains a class of the same name.  

```python
from PIL import Image
```

2. Create an Image object and call the open method on it. Make sure that you add the correct path for the image location - my image is in the same folder as my Python file, so I don't need to  add it. 

```python
img = Image.open('some-pic.jpg')
```

3. Save as a png image: specify the file name and the extention (format) to save the image in the same folder. You can also save the image in a different location by adding the file path.

```python
im.save('converted-pic.png')
```

The resulting Python code:

```python
import Image

img = Image.open('some-pic.jpg')
im.save('converted-pic.png')
```
