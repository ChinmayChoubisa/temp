# Lab Task-6 Crosslingual Transfer for Inflection Generation

## Morphological Generation -
Morphological generation may be considered an opposite task of morphological analysis. Here, given the description of a word in terms of number, category, stem, and so on, the original word is retrieved. For example, if root = go, part of speech = verb, tense= present, and if it occurs along with a third person and singular subject, then a morphological generator would generate its surface form, goes.

## About the task -
The task is the following: given a lemma and a bundle of morphological features, generate a target inflected form. The goal as instructed by sir (I have asked sir if I can do this or not instead of the task for single language and he agreed to this) is to perform morphological inflection in the low-resource language, having hopefully exploited some similarity to the high-resource language. Thus first the model for high resource language is trained(Hindi in Hindi--Bengali and German in German--middle-high-German). And then this model is used to train the model for the low resource language. 

Test input:

    body	V;V.PTCP;PRS
    randomise	V;V.PTCP;PST
Output:

    body	bodying	V;V.PTCP;PRS
    randomise	randomised	V;V.PTCP;PST

## Dataset used -
The dataset used is taken from the following git repository as instructed by sir:
> https://github.com/sigmorphon/2019/tree/master/task1

Two sets of two languages are taken from here-
- Hindi--Bengali Dataset (Hindi being the high resource language and Bengali being the low resource language)
- German--middle-high-German Dataset (German being the high resource language and middle-high-German being the low resource language)
 We can train the model of low resource language using the high resource language due to similarity in features such as same script.
 
 NOTE: The folder of the dataset used is inside the conll2019/task1/ folder inside the given link.
 
 ## Code used:
 I have used the code from the following git repository:
 > https://github.com/axsemantics/sigmorphon2019-task1
 
 I have asked sir if I can use this code and he said yes to this.
 
 The Jupyter Notebook for the respective dataset is uploaded here as well as in the folders that opens from the links.
 
 ***NOTE: In both the set of the languages we first train only the low resource data using the sigmorphan/all_train_2019task1.sh script and take it as the baseline(Mentioned in the Jupyter Notebook) and it makes the system_1. Then we train the cross-lingual model(as mentioned in the Jupyter Notebook)  
  and it makes system_2.*
## Libraries used:
- allennlp - AllenNLP is the deep learning library for NLP. Using AllenNLP to develop a model is much easier than building a model by PyTorch from scratch. Not only it provides easier development but also supports the management of the experiments and its evaluation after development.
- click - Click is a Python package for creating beautiful command line interfaces in a composable way with as little code as necessary.

NOTE: Debugging is required at one place after installing the allennlp library. Inside the usr/local/lib/python 3.7/dist-packages/allennlp/nn/beam_search.py at line 227 replace the line with this - backpointer = restricted_beam_indices // self.per_node_beam_size
