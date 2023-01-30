# NLP Data Scrubber using spacy library
Introduction
This is an NLP data scrubber model built using the spacy library to classify vendors from large groups of text such as credit card transactions, invoices, or transcribed dialog phone conversations. The result is derived from using the matcher library in spacy. The text is labeled after preliminary regex to remove special characters, etc.

# Libraries Used
spacy  
re (regex)  

import spacy  
import re  

# Load the spacy model
nlp = spacy.load("en_core_web_sm")

# Define the vendor patterns
vendor_patterns = [
    [{"LOWER": "amazon"},{"IS_DIGIT": True}],
    [{"LOWER": "starbucks"},{"IS_DIGIT": True}],
    [{"LOWER": "apple"},{"IS_DIGIT": True}]
    ]

# Initialize the matcher with the vendor patterns
matcher = spacy.matcher.Matcher(nlp.vocab)
for pattern in vendor_patterns:
    matcher.add("VENDOR", None, pattern)

# Define the function to classify the vendors
def classify_vendors(text):  
    ** Remove special characters  
        text = re.sub(r'[^\w\s]', '', text)    
    ** Pass the text to the nlp object  
        doc = nlp(text)  
    ** Get the matches  
        matches = matcher(doc)  
    ** Iterate through the matches and get the start and end positions  
        vendors = []  
        for match_id, start, end in matches:  
            span = doc[start:end]  
            vendors.append(span.text)  
        return vendors  

# Example usage
text = "I bought a coffee from Starbucks 123456 and an iPhone from Apple 654321"  
print(classify_vendors(text))  

# Output: ['Starbucks 123456', 'Apple 654321']


Conclusion
This model can be used to classify vendors from large groups of text. It uses the spacy library to perform NLP operations and the matcher library to match the patterns defined for vendors. The model can be easily extended to classify other entities by adding more patterns to the matcher.
