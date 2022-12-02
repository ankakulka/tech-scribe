---
title: "Merge PDFs Using Python"
date: 2022-11-30T11:47:12+01:00
draft: false
show_reading_time: true
featured_image: "/images/snake-selfcanibalising.png"
tags: ['python', 'PDF']
---

# Merge PDFs Using Python

Working with PDF files can a pain...but it doesn't have to be. 
You don't even need any expensive software to do that: just a few lines of Python code will suffice.
In this quick tutorial I'll show you how to easily merge multiple files without having to tinker in the Adobe Acrobat or a similar program. 
This method is much quicker and cheaper (all the tools used here are free).

> **Tip!** Some basic Python knowldege required!

1. Gather all PDFs you want to merge in the same folder. 
2. In the .py file 
 - Import PyPDF2 python library
 - Import PdfMerger class
 - Loop over the pdf files (it is handy to have them all in the same folder so you don't have to specify the full path)
 - Create a new pdf file with merger.write


 ```python
import PyPDF2
from PyPDF import PdfMerger
merger = PdfMerger()
for pdf in ["file1.pdf", "file2.pdf", "file3.pdf", "file4.pdf"]:
    merger.append(pdf)
merger.write("my-new-merged-file.pdf")
merger.close()
 ```