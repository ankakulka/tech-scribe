---
title: "Merge PDFs Using Python"
date: 2022-11-30T11:47:12+01:00
draft: false
show_reading_time: true
featured_image: "/images/snake-selfcanibalising.png"
tags: ['python', 'PDF', 'coding']
---

# Merge PDFs Using Python

Working with PDF files can a pain...but it doesn't have to be. 
You don't even need any expensive software to do that: just a few lines of Python code will suffice.
In this quick tutorial I'll show you how to easily merge multiple files without having to tinker in the Adobe Acrobat or a similar program, simply taking advantage of the capabilities of the PyPDF2 library.
This method is much quicker and cheaper (all the tools used here are free).     
I'm using Python version 3. 

> **Tip!** Some basic Python knowldege required!


1. Gather all PDFs you want to merge in the same folder. It is handy to have them all in the same folder so you don't have to specify the full path for each file.
2. Install the PyPDF2 package using pip: `pip install PyPDF2`
3.  Import PyPDF2 python library and PdfMerger class:
```python 
import PyPDF2
from PyPDF import PdfMerger
```
4. Create an object to hold the PdfMerger class.
`merger = PdfMerger()`
4. Loop over the pdf files. Use `append` method to attach files in consecutive order.
```python
for pdf in ["file1.pdf", "file2.pdf", "file3.pdf", "file4.pdf"]:
    merger.append(pdf)
```
5. Create a new pdf file using `write()` method on the merger object:
```python
merger.write("my-new-merged-file.pdf")
```
6. To close the program, use the `close()` method:
```python
merger.close()
```



The resulting Python code:

 ```python
import PyPDF2
from PyPDF import PdfMerger
merger = PdfMerger()
for pdf in ["file1.pdf", "file2.pdf", "file3.pdf", "file4.pdf"]:
    merger.append(pdf)
merger.write("my-new-merged-file.pdf")
merger.close()
 ```