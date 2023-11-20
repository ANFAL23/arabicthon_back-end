# arabicthon_back

# Silah - صلة
![Alt Text](Silah.png)



This repository contains the training script of our solution in the Arabicthon2023 in KSA.

## What is Arabicthon:

[Arabicthon](https://arabicthon.ksaa.gov.sa/) is a deep learning competition organized by [**The King Salman Global Academy for the Arabic Language**](https://ksaa.gov.sa/en/homepage/) on purpose to enrich Riyadh Dictionary.

## Our solution:

It is a website that facilitates arabic understanding throughout semantic relations between words, such as:

- Synonyms.
- Antonyms.
- Lexical field.
- Related words - Isomorphism.
- Hypernym.
- Hyponym.
- Object to instance relationship, etc.

The main features are : 

- Easy search for non-arabic speakers : We provide both arabic and english search with an automatic translation of english to arabic
- User-friendly vizualisation tools : Semantic relations are not just displayed as a boring list of words, however there are other appealing display modes like WordCloud and 3D Graph.
     * WordCloud : Helps the user visualize the most related words to the input word.
     * 3D Graph : Same advantage as a WordCloud, clickable nodes with another feature that enables the user to ...
- Assistance in learning semantic relations for beginners and advanced arabic learners, students and teachers and many more types of users! We provide an OCR tool that takes a text picture or PDF and detects all the relations in that text.
- Vocabulary quizzes : In order to enrich the database of Riyadh dictionary, we created smart quizzes for the users to check relations between given set of words, a double-edged sword Making the learner's experience more fun, improving the performance of our app!

## Front:

React app that contains the frontend of the project. you can find it in here: [https://github.com/mezdourcheima/arabicthon-front]()

## Backend:

Flask app that contains the backend of the project. you can find it in here: [arabicthon_backend]()

## Training:

### English to arabic translation :

This notebook covers machine translation backed by [Hugging Face models](https://github.com/neuml/txtai#egg=txtai[pipeline]) txtai an all-in-one embeddings database for semantic search, LLM orchestration and language model workflows. The quality of machine translation via cloud services has come a very long way and produces high quality results. You can find the training file in here: [en-to-ar-translation.ipynb]()


### Lexical field and vizualisation :

We used N-Grams model ported from [Aravec](github.com/bakrianoo/aravec), a pre-trained distributed word representation (word embedding) on more than 1M vocabularies. You can find the training files in here: [lexical-field-and-vizualisation-twitter.ipynb] ()

For word-similarity we used Embedding layers using cosine similarity.


### Synonyms, Antonyms and other semantic relations (Data) :

## arabic-read-wordnet : 

Extracting 4 relations from [AraWordNet](http://globalwordnet.org/resources/arabic-wordnet/) which are : hypernym, hyponym, has_instance, is_instance. 

## arabicLT : 

SQLite database and a CSV file with a comprehensive collection of Arabic synonyms, antonyms. You can find the database [here]()

## synset-sinalab-cleaned : 

A set of 500 synsets (extracted from the Arabic Wordnet). Each synset is enriched with a list of candidate synonyms. The total number is 3K candidates. Each candidate synonym is annotated with a fuzzy value.


### OCR and relation detection from image :

We used [tesseract 4](https://github.com/tesseract-ocr/tesseract) which adds a new neural net (LSTM) based OCR engine which is focused on line recognition, but also still supports the legacy Tesseract OCR engine of Tesseract 3 which works by recognizing character patterns.
