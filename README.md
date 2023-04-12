[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/ymop5HUw)
# CMPSC 310 Activity 15

## Deadline: April 12 by 9:50am

## Assignment

 For this activity follow [Neural machine translation with a Transformer and Keras](https://www.tensorflow.org/text/tutorials/transformer).

## Submission

Submit completed Colab notebook showing generated output.

## Data

The data from the tutorial is a dataset that contains translations for Portuguese and English (going either way). Pre-processing the data consisted of a few key steps beyond simply retrieving the data. The data had to first be tokenized, wherein each word (or subword, such as a common prefix/suffix) is converted into a numeric token ID. From there, the tokenized data had to be grouped into batches to be used for actually training the model.

## Transformer Components

### Embedding & Positional Encoding Layer

In effect, this first layer simply takes the batched tokenized data that has been pre-processed, and simply converts it into *vectors*. A vector--though seemingly complex at first blush--can be thought of as an object with two main properties: a *length*, and a *direction*. This "positional encoding" provided by a vector is important because it helps dictate the predicted "trajectory" of a sentence (wherein certain words almost always/never follow certain other words, helping to create semantic meaning within a sentence).

### Add & Normalize Blocks

These blocks occur frequently throughout the transformer; essentially, these are tailored blocks of code that take the output from one stage of the process and format it as a suitable input for the next stage. Nothing fancy, but incredibly important for efficient hand-off of outputs from one component of the transformer to the next.

### Cross Attention Layer

This layer can be thought of as the bridge between the otherwise separate encoder and decoder parts of the transformer (or more simply, input and output components).

### Global Self Attention Layer

After embedding (converting tokens to vectors, as you might recall), this layer is the first major layer for handling inputs in the transformer. Put most simply, this first layer allows every single element (or word, in this case) in the input to be compared against every other input, and essentially "scored" as match-ups.

### Causal Self Attention Layer

This layer is the first major layer in handling the *output* for the transformer. This in effect performs the same operation as the global self attention layer, comparing all elements in the embedded output against one another.
