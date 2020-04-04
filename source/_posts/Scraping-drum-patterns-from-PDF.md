---
title: Scraping drum patterns from PDF
date: 2020-02-20 18:48:17
tags:
---

Pocket JSON Ops is a rhythm dictionary taken from the book [Pocket Operations](https://b.shittyrecording.studio/file/shittyrec/print/Pocket+Operations+(2019-07-01).pdf), which compiles different percussion rhythms.

![alt text](pattern_example.jpg "Example of a book page")


## Why we did this?

In order to use the different rhythms compiled with different livecoding languages, convert the PDF into a beautiful JSON for the modern music computer. This was generated from an HTML version, generated from the PDF, and then analyzed using the Python Beautiful Soup 4 library.

## How to listen the patterns?

The `dpattern2foxdot.py` script contains an example of how patterns can be read and reproduced within FoxDot, Python's live music framework.