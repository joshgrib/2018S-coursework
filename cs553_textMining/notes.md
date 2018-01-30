<!-- markdownlint-disable MD007 -->
<!-- markdownlint-disable MD022 -->
<!-- markdownlint-disable MD032 -->
# CS 553 Notes

**Table of Contents:**
* [Module 0](#module-0-course-info)
    * [Schedule](#course-schedule)
    * [Assignments](#course-assignments)
    * [Using SAS in the course](#using-sas-in-the-course)
* [Module 1](#module-1-intro-SAS-install-getting-started)
    * [Assignment 1](#assignment-1-software-installation-and-data-file-preparation)
* [Module 2](#module-2-preparing-text-for-mining-and-analysis)
    * [Assignment 2](#assignment-2)
* [Module 3](#module-3-clustering-and-segment-profiling)
    * [Assignment 3](#assignment-3)
* [Module 4](#module-4-classification-prediction-decision-trees-and-rules)
    * [Assignment 4](#assignment-4)
* [Module 5](#module-5-text-topics-clusters-decision-rules)
    * [Assignment 5](#assignment-5)
* [Module 6](#module-6-by-hand-clustering)
    * [Assignment 6](#assignment-6)
* [Module 7](#module-7-info-extraction-named-entity-recognition-disambiguation)
    * [Assignment 7](#assignment-7)
* [Module 8](#module-8-case-studies)
    * [Assignment 8](#assignment-8)
* [Big takeaways](#big-takeaways)

## Module 0: course info
### Course Syllabus
#### Course Schedule
| Topic                                     | Readings         | HW     | Due Date    |
| :--                                       | :-:              | :-:    | :-:         |
| Getting started                           | Ch 1             | A01    | 20180130    |
| Preparing for text mining                 | Ch 2             | A02    | 20180221    |
| Clustering and segment profiling          | Ch 4.3-4.4, 5    | A03    | 20180310    |
| Classification prediction                 | Ch 3             | A04    | 20180324    |
| Text topics, clusters, decision rules     | Ch 3             | A05    | 20180407    |
| "By hand" clustering                      | Ch 2-5           | A06    | 20180421    |
| Info retrieval, term disambiguation       | Ch 4, 6          | A07    | 20180505    |
| Case studies or recent work               | Ch 8,9           | A08    | 20180516    |

#### Course Assignments
* **A01:** Software installation and data file preparation
* **A02:** Text parsing and concept associations
* **A03:** Clustering and segment profiling
* **A04:** Prediction, decision trees and rules
* **A05:** Text Topics, clusters, and decision rules
* **A06:** “By hand” tf-idf matrices and clustering
* **A07:** Page ranking, anchor text evaluation, and word sense disambiguation
* **A08:** Report on case study or a project of you own choosing

### "How to take the course" document
* Software
    * Mainly using SAS Text Miner, packages for Python, R, Java, C++, etc.
    * Professor likes R code most, then Java, if using python then you have to send kinda detailed instructions on how to run it.
    * There's a good Java API OpenNLP
    * You can use whatever you want as long as you satisfy the goals of the assignment
    * If you fnd good references put them in the dicsussion forum
* Course has both theory and practice, assignments are supposed to link them up and show the interralated roles of each. The theory should info why you're getting a certain output and how to interpret it
* Assignents can be done as groups, *but you must be in a group on Canvas, even if it's you alone in it*
* Assignment 8
    * Asks you to find and describe more recent text mining publications, public or private.  Read Chapters 8 and 9 early in the semester and throughout the semester look for write ups in the popular, technical, and academic press and web sites for descriptions of text mining projects. Choose one that is sufficiently detailed so that you could write a description analogous to the ones in Chapter 8
    * You can also do a project of your own with prior approval of the instructor

### Using SAS in the course
>[Good intro](http://support.sas.com/documentation/cdl/en/tmgs/65668/HTML/default/viewer.htm#titlepage.htm)
>[PDF Link](http://support.sas.com/documentation/cdl/en/tmgs/65668/PDF/default/tmgs.pdf)

* Document and data types
    * Numbers only - usually a table of values with headers and types
    * Some text variables - still a table type of thing, but with normal language text entries, such as responses to short-answer sections of a survey
    * Document collections - some text and numeric variables like author or title or ISBN, but mainly longer form text anywhere from a phrase or sentance length up to a full book

---

## Module 1: intro, SAS install, getting started
### Assignment 1: Software installation and data file preparation
>Due 20180130
#### Goal
Read introductory material. Install software and load a file containing at least one text field. Display some of the data/text within the software. If you have not done so already join one of the Assignment Groups even if you want to work by yourself. Limit 3 to a group
#### Notes
* I'm just following the guide from the modules
* [Useful link to get started with data](https://communities.sas.com/t5/SAS-Communities-Library/Tip-How-to-create-data-sources-from-imported-files-and-share/ta-p/221694)

#### Steps
* New project
* New Diagram
* Add File Import node to get source
* Add transformation now to add serious
    * In properties open up `Formulas`
    * Click the `Create` icon in the top left
    * Go to `Sample` in the bottom tabs to see the data

---

## Module 2: preparing text for mining and analysis
### Assignment 2

---

## Module 3: clustering and segment profiling
### Assignment 3

---

## Module 4: classification prediction: decision trees and rules
### Assignment 4

---

## Module 5: text topics, clusters, decision rules
### Assignment 5

---

## Module 6: "by hand" clustering
### Assignment 6

---

## Module 7: info extraction, named entity recognition, disambiguation
### Assignment 7

---

## Module 8: case studies
### Assignment 8

---

## Big takeaways