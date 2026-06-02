<H3 ALIGN=RIGHT> DATE:<H3>

<H1 ALIGN=CENTER> Experiment-6: Implementation of Semantic Analysis </H1>

### Name: Deekshitha K
### Register Number: 2305002005

## Aim: 

To perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques.

## Algorithm:

**Step-1:** Import the nltk library.

**Step-2:** Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.

**Step-3:** Accept user input for the text.

**Step-4:** Tokenize the input text into words using the word_tokenize function.

**Step-5:** Iterate through each word in the tokenized text.
-	 Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.
-	 Print each word along with its corresponding part-of-speech tag.
-	 For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).
-	 Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.
-  Print the unique sets of synonyms and antonyms.

## Program:

```
import nltk

nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')
nltk.download('averaged_perceptron_tagger_eng')

from nltk.tokenize import word_tokenize
from nltk.corpus import wordnet

sentence = input("Enter a sentence: ")

words = word_tokenize(sentence)

pos_tags = nltk.pos_tag(words)

synonyms = []
antonyms = []

for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append(lemma.name())

            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())

print("POS Tags:", pos_tags)
print("Synonyms:", set(synonyms))
print("Antonyms:", set(antonyms))
```
---

## Output:
<img width="1728" height="346" alt="image" src="https://github.com/user-attachments/assets/cf8b1908-682d-4e90-9949-b81a00525e13" />

---

## Result:
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
