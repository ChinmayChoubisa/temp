# Folder Structure:

	Main folder name: 19075024-Chinmay-Choubisa

	Main folder contain README.md, graph_outputs , model_weights, output and 2 .ipynb file of each language ,i.e. hindi and urdu.
	In the output folder there are feature_0(POS), feature_1(gender), feature_2(singular/pural), feature_3(person), feature_4(case), feature_5(tense-aspect-mood (TAM)).


# Motivation:

	To do morphological analysis for hindi and urdu (morphologically rich lannguages).


# Introduction:

	A morpheme is the smallest meaningful word in a sentence or a phrase in any language. In well-spaced sentences , Morphological Analysis(MA) is the first step in Neuro-Linguistic Programming(NLP), in which a sentence is divided into a sequence of morphemes and then we determine parts of speech of the segmented morpheme. Morphological analysis (MA) is a method for identifying, structuring and investigating the total set of possible relationships contained in a given multidimensional problem complex. MA allows small groups of subject specialists to define, link, and internally evaluate the parameters of complex problem spaces, creating a solution space and a flexible inference mode.


# Tools used:

	h5py, numpy, Keras, tensorflow, Keras-Applications, Keras-Preprocessing, PyYAML, matplotlib, scikit-learn


# Dataset used:

	Data used can be extracted from: http://ltrc.iiit.ac.in/hutb_release/


->All important results and scripts are available at link: https://drive.google.com/drive/folders/1Xyt5HwTsGkAmERpkU7li_tSCUFfrpnSV?usp=sharing


# Procedure:

	 1. train and test modes operate upon the standard train-test split specified by the HDTB and UDTB datasets
	 2. In model training, we are using convolutional neural network and recurrent neural networks model combined together(CNN-RNN model). The model will	predict Lemma, POS category, Gender, Number, Person, Case, and Tense-aspect-mood (TAM).
	 3. After train, test the model.
	 4. Last step is prediction. We have providedd data manually for prediction.
	 5. Commmands to execute 
	 	-> !pip install funcsigs
			!python main.py --lang urdu --mode train --phonetic true --freezing true # training 
		-> !python main.py --lang urdu --mode test --phonetic true --freezing true #test
		-> !python main.py --lang urdu --mode predict --phonetic true --freezing true #prediction
		Note: For Hindi dataset just replace "urdu" in above commands as "hindi"


# Results
	
	For urdu: 
		-> val_loss did not improve from 1.37210
		-> max time_dist_2_acc 0.9702 and val_time_dist_2_acc 0.9681
	For Hindi :
		-> val_loss improved from 0.80534 to 0.80222
		-> max time_dist_2_acc 0.9806 and val_time_dist_2_acc 0.9845
