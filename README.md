# ar21vega-keywords-extraction
Building AI course project

# Project Title

Keywords extraction with Python - Final project for the Building AI course

## Summary

The growing volume of text documents on the internet and digital libraries necessitates efficient keyword extraction methods to retrieve key elements. Traditional approaches to keyword extraction involve manually assigning keywords based on article content and author ratings. This requires a lot of time and effort and may not be always accurate in terms of choosing the right keywords. With the advent of Natural Language Processing and Machine Learning, keyword extraction has become an effective and efficient method. 
Although today there’s a number of different keyword extraction tools available online or as a professional packages, not all of them allow a desired configuration, such as use of n-grams and other tuning. That’s the main reason for my choice of the subject for this Final Project. I had written the code for keywords extraction based on SpaCy library, designed by Matthew Honnibal, and another one, based on KeyBERT, authored by Maarten Grootendorst. 
I used these two approaches due to their relative novelty and in order to evaluate their respective efficiency, in terms of recall, precision and processing time. Though, in the present case, both models return almost identical results, a used data set is too small to make some generalizations.  


## Background

Although there’s today a number of different keyword extraction tools available online or as a professional packages, not all of them allow a desired configuration, such as use of n-grams and other tuning. That’s the main reason for my choice of the subject for this Final Project. 
In practical terms, a handy tool for the batch processing of an articles' set, should significantly icrease the productivity of an involved staff, while the productivity is still the common and major priority in evaluation of the performance of an employee.                                       

My motivation and interest in the keywords extraction methods results from my regular work with articles’ abstracting and indexing. Keywords are an important component in research and news articles, providing a concise representation of the article's content and categorizing it into the relevant subject. They play a crucial role in locating the article, enhancing search engine optimization, and locating it in information retrieval systems and bibliographic databases. It’s also impossible overrate its influence on the raise of indexing productivity in context of the growing volume of text documents to process. 

## How is it used?

I had written the code for keywords extraction based on SpaCy library, designed by Matthew Honnibal, and another one, based on KeyBERT, authored by Maarten Grootendorst. 
I used these two approaches due to their relative novelty and in order to evaluate their respective efficiency, in terms of recall, precision and processing time. Though, in the present case, both models return almost identical results, a used data set is too small to make some generalizations. 
The demo of both applications is shown below.

Describe the process of using the solution. In what kind situations is the solution needed (environment, time, etc.)? Who are the users, what kinds of needs should be taken into account?

Images will make your README look nice!
Once you upload an image to your repository, you can link link to it like this (replace the URL with file path, if you've uploaded an image to Github.)
![Cat](https://....jpg)

To resize images, you have to use an HTML tag, like this:
<img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/Sleeping_cat_on_her_back.jpg" width="200">

This is how you create code examples:
```
def main():
   countries = ['Denmark', 'Finland', 'Iceland', 'Norway', 'Sweden']
   pop = [5615000, 5439000, 324000, 5080000, 9609000]   # not actually needed in this exercise...
   fishers = [1891, 2652, 3800, 11611, 1757]

   totPop = sum(pop)
   totFish = sum(fishers)

   # write your solution here

   for i in range(len(countries)):
      print("%s %.2f%%" % (countries[i], 100.0))    # current just prints 100%

main()
```


## Data sources and AI methods

Keywords are extracted from the dataset that contains about 12,988 words. This is a sub-set of an original dataset 'A study of Asian Religious and Biblical Texts' from UCI Machine Learning Repository (https://archive.ics.uci.edu/dataset/512/a+study+of+asian+religious+and+biblical+texts). 

Dataset Characteristics: Multivariate, Text, Sparse Data; Subject Area: Social, Religion.

The choice of this dataset is stimulated by my current work with the similar materials. The complete dataset includes five subsets labeled as Buddhist Sutras, Upanishads, TaoTeKing, Yoga Sutras, and Biblical texts. Each subset concerns different religious traditions with their specific concepts and descriptors that carries different interpretation, in the related tradition. Therefore, for the sake of their adequate interpretation, the complete dataset was divided into the five subsets for the keyword extraction. 
The test sets (keywords-candidates), the 'ground truth' datasets for each subset, are selected based on the religious thesauri for each of the concerned religious traditions. 
The present prototype represents an application of our coding to the one of these subsets, the Buddhist Sutras. 


## Challenges

A further improvement of the script, with including the ‘create candidates’ snippet by  Maarten Grootendorst, and possibly the Flair embeddings developed by Humboldt University of Berlin.

## What next?

Finally writing a script to convert the Python file to a Windows executable, in order to deliver a small open source tool for colleagues,            in area of publishing and research.


## Acknowledgments

* list here the sources of inspiration 
* do not use code, images, data etc. from others without permission
* when you have permission to use other people's materials, always mention the original creator and the open source / Creative Commons licence they've used
  <br>For example: [Sleeping Cat on Her Back by Umberto Salvagnin](https://commons.wikimedia.org/wiki/File:Sleeping_cat_on_her_back.jpg#filelinks) / [CC BY 2.0](https://creativecommons.org/licenses/by/2.0)
* etc
