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

![word vector](latex/word_vec.svg) <!-- .element class="medium" -->

---

## Words and Phrases

Instead of doing just single words, we can also extend this approach to phrases, which are often called **n-grams**, or more generally **tokens**

Popularized by Google's handy Ngram viewer

![google ngram](images/google_ngram.png) <!-- .element class="large" -->

---

## Long Tail

Common words such as "the", "and", and "of" account for large share of words, with many rare words in the tail

![freq_dist](images/freq_dist.svg)

---

## Normalization

Not all words are created equal, some are more interesting than others
- generally the more rare a word is, the more interesting it is

A common approach here is to upweight words that are less common
\\[ w_k = \log\left(\frac{D}{d_k}\right) \\]
where $d_k$ is the number of documents featuring token $k$ and $D$ is the total number of documents

---

## Document Similarity

Once we have vectorized our documents, computing the similarity between them is straightforward

We use a metric called a **cosine similarity** that gives us a number between 0 and 1 representing how similar two vectors are

Mathematically, if we have word vectors $c_1$ and $c_2$, we would calculate the vector product between the two

\\[ \text{Similarity} = \frac{c_1 \cdot c_2}{||c_1|| \cdot ||c_2||} \\]

---

## Similarity Example

![doc_sim](latex/doc_sim.svg) <!-- .element class="large" -->

---

## Computing Similarity

So we get 7, but what does that mean? We need to divide by some baseline to get between 0 and 1

Comparing the first (blue) sentence with itself would give 13, while the same for the second (red) sentence is 15, thus the average of 14 seems good
- then we get $7/14 = 0.5$ for out similarity

Does this seem reasonable? The word "the" is doing a lot of work here, that's why we should downweight common words!
- if we do the same thing but ignore "the" and "in", we get $1/7 \approx 0.15$

---

## Document Classification

Instead of comparing pairs of documents, we might want to group them into broad categories

We could just group documents with high similarity together, but it turns out there are better ways
- prime example is known as **k-means clustering**

Choose a number of groups $k$ (say 5) and this will assign each document to groups so that each group is as dense as possible in terms of similarity
- you must give meaning to the groups though (we'll see this)

---

## Machine Learning

With machine learning we can do an even better job of classifying documents, but we need big training sets
- this allows you to both classify and go in reverse to generate synthetic documents (see GPT-2 from OpenAI)

Synth Moby

---

## Tools

The go to language for text analysis today is Python

Everything we've discussed today can be done using the `sklearn` package

For a more linguistically oriented word-level analysis, `NLTK` is also very useful

---

## Jupyter Example



---

## Case Study 1

Wikipedia
- document similarity
- evolution of documents

---

## Case Study 2

Patents to Products
- document clustering
- document categorization

---

## Other Uses

---

## More Resources
