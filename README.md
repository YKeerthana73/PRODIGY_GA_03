# PRODIGY_GA_03
# Markov Chain Text Generator

## Overview
This project implements a simple Markov Chain text generator using Python. The generator learns from a given text and produces new sentences based on the probabilities of word sequences in the training data.

## Table of Contents
1. **Requirements**
2. **Class Structure**
   - MarkovChain Class
3. **Methods**
   - `__init__`
   - `train`
   - `generate_text`
4. **Usage**
5. **Example**

---

## 1. Requirements
- Python 3.x
- No external libraries are required beyond the standard library.

## 2. Class Structure

### MarkovChain Class
The `MarkovChain` class is responsible for storing the transition probabilities of words based on the training data.

- **Attributes:**
  - `transitions`: A nested dictionary that holds the probabilities of moving from one word to another.

## 3. Methods

### `__init__`
```python
def __init__(self):
    self.transitions = defaultdict(lambda: defaultdict(float))
```
- **Initializes the MarkovChain instance and sets up a nested dictionary to hold word transitions.**
## `train`
```python
def train(self, text):
    ...
```
`Input`: A string `text` containing the training data.
- **Process:**
  - Splits the text into words.
  - Iterates through the words, counting occurrences of transitions from each word to the next.
  - Normalizes the counts to create probabilities for each transition.
### `generate_text`
```python
def generate_text(self, length=10):
    ...

```
- **Input**:An optional integer `length` specifying how many words to generate (default is 10).
-  **Process:**
  - Randomly selects a starting word from the training data.
  - Uses the transition probabilities to generate a sequence of words.
  - Returns the generated text as a string.
## 4. Usage
To use the Markov Chain text generator:

1. **Import the MarkovChain class.**
2. **Create an instance of MarkovChain.**
3. **Train the model with a sample text using the `train` method.**
4. **Generate text using the `generate_text` method.**
## 5. Example
Here’s a simple example to illustrate how to use the Markov Chain text generator:

```python
if __name__ == "__main__":
    sample_text = (
        "the small brown dog jumped over the lazy cat. "
        "the lazy cat slept while the small dog barked. "
        "he saw the quick brown fox."
    )

    markov_chain = MarkovChain()
    markov_chain.train(sample_text)

    generated_text = markov_chain.generate_text(10)
    print("Generated Text:")
    print(generated_text)
```
The above example will output a randomly generated sequence of words based on the provided `sample_text`.

  
