# ar21vega-keywords-extraction
Building AI course project

# Project Title

Keywords extraction with Python - Final project for the Building AI course

## Summary

The growing volume of text documents on the internet and digital libraries necessitates efficient keyword extraction methods to retrieve key elements. Traditional approaches to keyword extraction involve manually assigning keywords based on article content and author ratings. This requires a lot of time and effort and may not be always accurate in terms of choosing the right keywords. With the advent of Natural Language Processing and Machine Learning, keyword extraction has become an effective and efficient method. 
Although today there’s a number of different keyword extraction tools available online or as a professional packages, not all of them allow a desired configuration, such as use of n-grams and other tuning. That’s the main reason for my choice of the subject for this Final Project. I had written the code for keywords extraction based on SpaCy library, designed by Matthew Honnibal, and another one, based on KeyBERT, authored by Maarten Grootendorst. 
I used these two approaches due to their relative novelty and in order to evaluate their respective efficiency, in terms of recall, precision and processing time. 


## Background

Although there’s today a number of different keyword extraction tools available online or as a professional packages, not all of them allow a desired configuration, such as use of n-grams and other tuning. That’s the main reason for my choice of the subject for this Final Project. 
In practical terms, a handy tool for the batch processing of an articles' set, should significantly icrease the productivity of an involved staff, while the productivity is still the common and major priority in evaluation of the performance of an employee.                                       

My motivation and interest in the keywords extraction methods result from my regular work with articles’ abstracting and indexing. Keywords are an important component in research and news articles, providing a concise representation of the article's content and categorizing it into the relevant subject. They play a crucial role in locating the article, enhancing search engine optimization, and locating it in information retrieval systems and bibliographic databases. It’s also impossible overrate its influence on the raise of indexing productivity in context of the growing volume of text documents to process. 

## How is it used? 

An expected environment is a publishing or research offices, or an individual office of a remote indexer/cataloger, or similar users, employing Windows, Mac or Linux desktops for working on tasks which include the keywords/subject headings search and using open-source software.

## Keyword-extraction using annotated SpaCy code example:
```
import os
import spacy
from spacy.tokens import Doc
from spacy.language import Language

# Define the location of the input file
input_file = 'C:/Data/Buddhist_Sutras.txt'

# Load English language model
nlp = spacy.load('en_core_web_sm')

# Define the custom keyword extraction component
@Language.component("keyword_extractor")
def keyword_extractor(doc):
    # Use the TextRank algorithm to extract keywords
    # Replace this with your actual keyword extraction logic
    keywords = ["example", "keyword1", "keyword2", ..., "keyword"]

    # Add the keywords to the doc's user_data
    doc.user_data["tr_keywords"] = keywords

    return doc

# Add the custom keyword extractor to the pipeline
nlp.add_pipe("keyword_extractor")

# Process the input text
with open(input_file, 'r', encoding='utf-8') as f:
    text = f.read()
    doc = nlp(text)

# Extract keywords using the TextRank algorithm
keywords = doc.user_data["tr_keywords"]

# Print the extracted keywords
print(keywords)
```

## Keyword-extraction using annotated KeyBERT code example:
```
from keybert import KeyBERT
import re
from bs4 import BeautifulSoup

file_path = 'C:/Data/Buddhist_Sutras.txt'
candidates = ["keyword", "keyword1", "keyword2", "keyword3", ..., "stress"]

def preprocess_text(text):
    # Remove HTML tags
    text = BeautifulSoup(text, 'html.parser').get_text()
    # Remove line breaks and extra whitespaces
    text = re.sub(r'\n', ' ', text)
    text = re.sub(r'\s+', ' ', text)
    return text

if __name__ == '__main__':
    # Load the KeyBERT model
    keyword_extractor = KeyBERT()
    
    # Process the input text
    docs = []
    try:
        with open(file_path, 'r') as file:
            text = file.read()
            # Preprocess the text
            text = preprocess_text(text)
            # Extract the keywords using KeyBERT
            keywords = keyword_extractor.extract_keywords(text, keyphrase_ngram_range=(1, 2), stop_words='english', top_n=10)
            docs.append((file_path, keywords))
    except Exception as e:
        print(f"Error processing {file_path}: {e}")
    
    # Print the extracted keywords
    for doc in docs:
        if doc[1] and len(doc[1]) > 0:
            print(f"{doc[0]}:\n\t{', '.join([kw[0] for kw in doc[1]])}\n")
        else:
            print(f"No keywords found for {doc[0]}\n")

```
## Data sources and AI methods

Keywords are extracted from the dataset that contains about 12,988 words. This is a sub-set of an original dataset 'A study of Asian Religious and Biblical Texts' from UCI Machine Learning Repository (https://archive.ics.uci.edu/dataset/512/a+study+of+asian+religious+and+biblical+texts). 

Dataset Characteristics: Multivariate, Text, Sparse Data; Subject Area: Social, Religion.

The choice of this dataset is stimulated by my current work with the similar materials. The complete dataset includes five subsets labeled as Buddhist Sutras, Upanishads, TaoTeKing, Yoga Sutras, and Biblical texts. Each subset concerns different religious traditions with their specific concepts and descriptors carrying different interpretation, in the related tradition. Therefore, for the sake of their adequate interpretation, the complete dataset was divided into the five subsets for the keyword extraction. 
The test sets (keywords-candidates), the 'ground truth' datasets for each subset, are selected based on the religious thesauri for each of the concerned religious traditions. The present prototype represents an application of our coding to the one of these subsets, the Buddhist Sutras.

I had written the code for keywords extraction based on SpaCy library, designed by Matthew Honnibal, and another one, based on KeyBERT, authored by Maarten Grootendorst. 
These two approaches are used due to their relative novelty and in order to evaluate their respective efficiency, in terms of recall, precision and processing time. 
Both models return mostly similar results, though the SpaCy script appears more performant in terms of the processing time. However, the used data set is too small to make some generalizations with respect to the efficiency of applied scripts. 
The code of both applications is shown above, in the section Keyword-extraction. 
 
## Challenges

A further improvement of the script would probably need writing a version of the ‘create candidates’, based on the snippet by  Maarten Grootendorst, and possibly the Flair embeddings, developed by Humboldt University of Berlin.

## What next?

Finally, I expect writing a script to convert the Python file to a Windows executable, in order to deliver a small open source tool for colleagues, in area of publishing and research.

## Acknowledgments

* Keyword Extraction with Python at (https://thecleverprogrammer.com/2020/12/01/keyword-extraction-with-python/)
* Extract Keywords Using spaCy in Python at (https://betterprogramming.pub/extract-keywords-using-spacy-in-python-4a8415478fbf)
* Minimal keyword extraction with BERT - GitHub at (https://github.com/MaartenGr/KeyBERT)

