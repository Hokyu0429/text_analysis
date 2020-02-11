<br/>

# Text Analysis Methods

<br/>

### Douglas Hanley
### University of Pittsburgh
### Spring 2020

---

## Approaches

Constructing metrics for document similarity

---

## Vectorization

The fundamental approach here is to turn textual data into numerical data

Any string of words can be turned into a vector by counting up the number occurances of each word

![document vector](images/document_vector.png) <!-- .element class="large" -->

---

## Terminology

**Token**: a single word or phrase, sometimes called *n-grams* for length "n" phrases

**Document**: any piece of text ranging in size from a tweet to an article to an entire book

**Corpus**: a collection of documents, potentially having some common origin

---

## Normalization

Not all words are created equal, some are more interesting than others
- generally the more rare a word is, the more interesting it is

A common approach here is to downweight words that are more common
\\[ w_k = \log\left(\frac{D}{d_k}\right) \\]
where $d_k$ is the number of documents featuring token $k$ and $D$ is the total number of documents

---

## Words and Phrases
