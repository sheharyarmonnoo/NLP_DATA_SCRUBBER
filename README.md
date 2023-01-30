# NLP Data Scrubber using spaCy library
Introduction
This is an NLP data scrubber model built using the spacy library to classify vendors from large groups of text such as credit card transactions, invoices, or transcribed dialog phone conversations. The result is derived from using the matcher library in spacy. The text is labeled after preliminary regex to remove special characters, etc.

## Why use spaCy?

spaCy has a powerful matching library called the matcher that can be used to match specific patterns in text, making it suitable for the task of classifying vendors from text. 

- It provides fast and efficient tools for NLP tasks such as tokenization, POS tagging, and NER.
- It has a powerful matching library called the matcher, suitable for classifying vendors from text.
- It provides pre-trained models that can be easily loaded and used, reducing the need for extensive data preparation and feature engineering.

# Libraries Used
spacy  & re (regex)  

# Load the spacy model
nlp = spacy.load("en_core_web_sm")

# Defining vendor patterns
vendor_patterns = [
    [{"LOWER": "amazon"},{"IS_DIGIT": True}],
    [{"LOWER": "starbucks"},{"IS_DIGIT": True}],
    [{"LOWER": "apple"},{"IS_DIGIT": True}]
    ]

# Example usage
text = "I bought a coffee from Starbucks 123456 and an iPhone from Apple 654321"  
print(classify_vendors(text))  

# Output: ['Starbucks', 'Apple']


Conclusion
This model can be used to classify vendors from large groups of text. It uses the spacy library to perform NLP operations and the matcher library to match the patterns defined for vendors. The model can be easily extended to classify other entities by adding more patterns to the matcher.
