<!-- markdownlint-disable MD007 -->
<!-- markdownlint-disable MD022 -->
<!-- markdownlint-disable MD032 -->
<!-- markdownlint-disable MD024 -->
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
* Go to the SAS website `https://odamid.oda.sas.com/SASODAControlCenter/`
* Log in, select `SAS® Enterprise Miner™`
* Run the file to start the program
* New project
* New Diagram
* In the top toolbar, go to `Sample`>`File Import` , add this as the first node in the diagram
    * Under the node properties select `Import File` and navigate to the file with the data
* Add a `Modify`>`Transform Variables` node, connect the `File Import` node to it
    * In properties open up `Formulas`
    * Click the `Create` icon in the top left
    * Create the formula for the variable you want
        * `Name` is `SERIOUS`
        * Formula is `SUBSTRN('NY', (DIED = 'Y' | ER_VISIT='Y' | HOSPITAL='Y' | DISABLE='Y')+1, 1)`
            * In the inner parenthesis this checks if those columns have a `Y` value, which return a 0 or 1
            * Then we take a substring of `NY`, starting at 1 or 2(I guess that's how SAS does indexing) and taking 1 character
            * So if any columns are `Y` we get a 1 and take the second character, `Y`, otherwise we get the first, `N`
    * Go to `Sample` in the bottom tabs to see the data

---

## Module 2: preparing text for mining and analysis
### Assignment 2
>Due 20180221
#### Goal
Separate the data set into randomly selected training, validation, and testing partitions; in SAS, this may have to be done first. Show the results of parsing and filtering the document corpus, showing words, terms, tokens, lemmata, parts of speech, special and multi-word features, and their frequencies. Create and show the term frequency/inverse document frequency (tf-idf) table. Show concepts from frequent term associations in a table or graph to identify frequent, possibly non-contiguous, multi-word combinations that might have importance in the text
#### Notes
* Lecture focussed on different theories and methods of breaking down text into meaningful chunks to compare - parts of speech, relation in distance to other words, using roots of words to find different versions of the same word and relating it to a particular usage
* For assignment - **compare results when using partitions(training, validating, testing) to not using partitioning, and try a few different partition percentages**
* Tutorial: https://support.sas.com/documentation/cdl/en/tmgs/65668/PDF/default/tmgs.pdf
#### Steps
1. Read material for the week
2. Open SAS, add the data, get oriented
3. Follow the tutorial for chapter 4 up to clustering

---

## Module 3: clustering and segment profiling
### Assignment 3
#### Goal
Without using the target variable nor its constituents, cluster the rows of the data set into both a given number of clusters and the number of cluster the software determines without input from the user (if it can do that). Clusters are also called segments. Interpret how the observations in each cluster are like each other and different from the other clusters, and how variable values distributions in each cluster compare to their distributions in the entire data set.  Give the clusters a short, descriptive name. Interpret the characteristics of the important variables and descriptive terms for each cluster/segment considering the proportions of the target variable values for that segment; do they suggest the proportion of observations with various values of the target variable are different in the various segments?  This is ultimately one of the goals of clustering and population segmentation.  Clustering is unsupervised so no partitions are needed but may be used by the software to test the cluster for some optimality.
#### Notes
#### Steps

---

## Module 4: classification prediction: decision trees and rules
### Assignment 4
#### Goal
#### Notes
#### Steps

---

## Module 5: text topics, clusters, decision rules
### Assignment 5
#### Goal
#### Notes
#### Steps

---

## Module 6: "by hand" clustering
### Assignment 6
#### Goal
#### Notes
#### Steps

---

## Module 7: info extraction, named entity recognition, disambiguation
### Assignment 7
#### Goal
#### Notes
#### Steps

---

## Module 8: case studies
### Assignment 8
#### Goal
#### Notes
#### Steps

---

## Big takeaways