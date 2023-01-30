# NLP Data Scrubber using spaCy library
Introduction
This is an NLP data scrubber model built using the spacy library to classify vendors from large groups of text such as credit card transactions, invoices, or transcribed dialog phone conversations. The result is derived from using the matcher library in spacy. The text is labeled after preliminary regex to remove special characters, etc.

## Why spaCy?

spaCy is a popular natural language processing (NLP) library in Python. 

- It provides pre-trained models that can reduce the need for extensive data preparation and feature engineering.
- It provides fast and efficient tools for NLP tasks such as tokenization, POS tagging, and NER.
- It has a powerful matching library called the matcher, suitable for classifying vendors from text.


#### Libraries Used
spacy  & re (regex)  

#### Loading the spacy model
spacy.load("en_core_web_sm")

"en_core_web_sm" stands for "English Core Web Small". 

- The "Core" part refers to the fact that it's a basic model that covers the most common NLP tasks, such as tokenization, part-of-speech (POS) tagging, and named entity recognition (NER). 
- The "Web" part refers to the fact that it was trained on a diverse mix of web-based text. The "Small" part refers to its size, which is relatively compact compared to other spaCy models. 
- The "sm" model is a smaller and faster version of the full spaCy English model. It is a good choice for projects that require NLP capabilities, but have limited computational resources.  



#### Defining vendor patterns
[[{"LOWER": "amazon"},{"IS_DIGIT": True}], [{"LOWER": "starbucks"},{"IS_DIGIT": True}], [{"LOWER": "apple"},{"IS_DIGIT": True}] ]

#### Example usage
"I bought a coffee from Starbucks on 13th Street and an iPhone from Apple down at Yale and Harvard"  
  
Output: ['Starbucks', 'Apple']


## Conclusion
This NLP data scrubber model can be useful for businesses and organizations that need to process large amounts of text data such as credit card transactions, invoices, or transcribed dialog phone conversations. Some examples of businesses that can benefit from this model include:

- Financial institutions (e.g. banks, credit card companies)
- Retail companies (e.g. online marketplaces, brick and mortar stores)
- Telecommunications companies (e.g. phone service providers)
- Payment processors (e.g. PayPal, Square)
- Supply chain management companies

In general, any business that needs to categorize or extract information from large amounts of text data can benefit from this model. 

The model was result of the following steps:

- Data Collection
- Data Preproceesing
- Manual Annotation
- Training and Evaluation 
- Tuning to buisness specfic requirements

Message me to host a live preview of the model in action.
