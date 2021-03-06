# Att-ChemdNER
***
This repo contains the source code and dataset for the following paper:
- [Ling Luo, Zhihao Yang, Pei Yang, Yin Zhang, Lei Wang, Hongfei Lin, Jian Wang. An Attention-based BiLSTM-CRF Approach to Document-level Chemical Named Entity Recognition. Bioinformatics, 2017.](https://academic.oup.com/bioinformatics/advance-article-abstract/doi/10.1093/bioinformatics/btx761/4657076?redirectedFrom=fulltext)
## Dependency package

Att-ChemdNER uses the following dependencies:

- [Python 2.7](https://www.python.org/)
- [Theano 0.9.0](http://www.deeplearning.net/software/theano/)
- [numpy 1.12.1](http://www.numpy.org/)


## Content
- data
	- CHENDNER corpus
	- CDR corpus
- models
	- The basic BiLSTM-CRF model
	- The Att-BiLSTM-CRF model
	- The 50-dimensional word embedding
- src
	- backend
	- evaluation: evaluate result of NER task
	- activations.py: activation functions
	- initializations.py
	- loader.py: load the data set
	- model.py: build the model
	- nn.py: the layers of the network architecture
	- optimizaiton.py: optimization method
	- utils.py
	- train.py: train a basic BiLSTM-CRF model
	- AttenTrain.py: train a Att-BiLSTM-CRF model
	- tagger.py: tag the document using the BiLSTM-CRF model
	- AttenTrain.py: tag the document using the Att-BiLSTM-CRF model

## Train a basic BiLSTM-CRF model
To train a basic BiLSTM-CRF model, you need to provide the file of the training set, development set,testing set and word embedding model, and run the train.py script:

```
python train.py --train trainfile --dev devfile --test testfile --pre_emb word_embedding.model 
```
## Train a Att-BiLSTM-CRF model
To train our Att-BiLSTM-CRF model, you need to provide the file of the training set, development set,testing set and word embedding model, and run the AttenTrain.py script:

```
python AttenTrain.py --train trainfile --dev devfile --test testfile --pre_emb word_embedding.model 
```
## Tag the documents using the BiLSTM-CRF model
Recognize the chemical entities from the documents using the pretrained BiLSTM-CRF model, and you need to provide the pretrained model, inputfile and outputfile:

```
python tagger.py --model BiLSTM-CRF.model --input inputfile --output outputfile
```
The inputfile should contain one document by line, and they have to be tokenized.

## Tag the documents using the Att-BiLSTM-CRF model
Recognize the chemical entities from the documents using the pretrained Att-BiLSTM-CRF model, and you need to provide the pretrained model, inputfile and outputfile:

```
python Atten_tagger.py --model Att-BiLSTM-CRF.model --input inputfile --output outputfile
```

The inputfile should contain one document by line, and they have to be tokenized.


***

