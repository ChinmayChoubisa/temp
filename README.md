#Lab Task 7 - Bilingual Dictionary Induction Using Lexical Transfer and comparable Corpora.


### Folder Structure :

There is a main folder named 19075024-Chinmay-Choubisa. This folder contains two folder <br>
(i) Word2Vec <br>
(ii) Fast_Text

These two folders have thererespective .ipynb files and since the size of models were very large, so i copied the google drive link which contains the models.

Here is the google drive link containing my models-

https://drive.google.com/drive/folders/1_y9Q4E8MHDFUJK0tYp4-_Hki6LxFv6FQ?usp=sharing



### Task Intro :

1). **Word2Vec** - Word2vec is the technique/model to produce word embedding for better word representation. It captures a large number of precise syntactic and semantic word relationship. It is a shallow two-layered neural network. <br> Word2vec is an algorithm used to produce distributed representations of words, and by that we mean word types; i.e. any given word in a vocabulary, such as get or grab or go has its own word vector, and those vectors are effectively stored in a lookup table or dictionary. <br>
2). **Fast Text** - FastText is an open-source, free, lightweight library that allows users to learn text representations and text classifiers. It works on standard, generic hardware. Models can later be reduced in size to even fit on mobile devices. <br> FastText uses a simple and efficient baseline for sentence classification( represent sentences as bag of words (BoW) and train a linear classifier). It uses negative sampling , hierarchical softmax and N-gram features to reduce computational cost and improve efficiency. <br> Although it takes longer time to train a FastText model (number of n-grams > number of words), it performs better than Word2Vec and allows rare words to be represented appropriately.

### Languages used :

In this task, I used German and English datasets and produced the provided models and results using datasets of these languages.


### Procedure :

1) First of all, we downloaded the datasets of both the languages used , i.e. German and English.
2) Then we extracted (unzipped) the datasets.
3) After this, data was preprocessed of both the languages.
4) Now, it was time to create the models and embedding mapping was applied on the models.
5) Finally, models were tested and accuracy and other parameters were calculated.

The difference between the two methods is that in Fast text , we downloaded the models and extracted them. After this all the steps were same.

### Accuracy :

After that I calculated the accuracy for both the Word22Vec and the Fast text methods using a testing dictionary, i got the following results -

(i) Word2Vec - 

|                   | Coverage | Accuracy |
|-------------------|----------|----------|
| English to German |  98.35%  |  38.59%  |
| German to English |  97.05%  |  38.54%  |

(ii) Fast text - 

|                   | Coverage | Accuracy |
|-------------------|----------|----------|
| English to German |  99.55%  |  63.99%  |
| German to English |  99.40%  |  62.22%  |



### Conclusion :

The accuracy of the dictionaries generated from using the Word2Vec embeddings are much less than that we receive from using the Fasttext embeddings.


1). Word2vec treats each word in a corpus like an atomic entity and generates a vector for each word ,thus word2vec treats words as the smallest unit to train on. <br>
FastText which is essentially an extension of the word2vec model — treats each word as composed of character n-grams. So the vector for a word is made of the sum of this character n-grams.

2). The amount of corpus on which I trained the word2vec embeddings was comparitively small due to computational inefficiencies , the embeddings generated were not that good and so the accuracy of the dictionaries generated was less.
