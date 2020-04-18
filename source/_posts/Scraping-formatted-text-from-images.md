---
title: Scraping formatted text from images
date: 2019-10-03 13:28:21
tags: ocr
cover_image: images/ocr.jpg
---

# Image to Text conversion utilities

You can find [here](https://github.com/mathigatti/img2txt) a small tokenization utility and examples of table extraction from images using Google Vision API. Google provides a good OCR to extract text from images but the output is not the best sometimes, in this repository I provide a simple postprocessing of the output in order to make it easier to use the API output.

## Motivation

Google OCR provides a text output which might not have the expected format, if that's the case it also provides a JSON output with information about the position of each recognized entity. The problem is that this data is not so well structured for some tasks, extracting tokens (Series of characters without spaces between each other) is not so easy with this JSON since it doesn't provides directly this information. The goal of this is to provide a way to postprocess this data into something more maneagable, so it's more appropiate for text processing tasks like extracting full lines of text or filtering words.

In order to do this a postprocessing code is provided at `src/image2tokens.py`. This is applied in order to extract tokens and then even more abstract concepts like text lines or table columns.

## Demo

### Sample Input

<img src="https://github.com/mathigatti/img2txt/blob/master/sample/input/sample.png?raw=true" width="100%" border="5" />

### Sample Output
```
                          HR Information                                 Contact
                                Position                                  Salary                                  Office                                   Extn.
                              Accountant                                $162,700                                   Tokyo                                    5407
           Chief Executive Officer (CEO)                              $1,200,000                                  London                                    5797
                 Junior Technical Author                                 $86,000                           San Francisco                                    1562
                       Software Engineer                                $132,000                                  London                                    2558
                       Software Engineer                                $206,850                           San Francisco                                    1314
                  Integration Specialist                                $372,000                                New York                                    4804
                       Software Engineer                                $163,500                                  London                                    6222
                       Pre-Sales Support                                $106,450                                New York                                    8330
                         Sales Assistant                                $145,600                                New York                                    3990
             Senior Javascript Developer                                $433,060                               Edinburgh                                    6224
```