# Fake-News-Detection


## Introduction
We will code ML techniques in ython on our fake news dataset in order to elect best algorithm o be used in detecting fake news. A very important question rises will the machine learning techniques will give accuracy ad validation results to that of by any human? Hence, for the uestion to be answered we will be using three different echniques. Obviously 100% accuracy can’t be achieved till now by any algorithm but the model with the highest accuracy approximately in 90s will be close enough to be equivalent to the results attained by humans.
The whole project has been decided to be programmed in python. The reason for selecting python is due to its simplicity and understandability no matter how complex the code is. In addition, it offers a lot of libraries and modules to support the whole machine learning process.

## Guide to use
  - Download the files
  - Open Data preparation and make word2vec of your data and save .npz files and other necessary files for training.
  - Open Config.py and adjust it according to your setup and adjust related file paths in it.
  - To modify training loss and optimizer open train.py and edit it.
  - To start training run train.py

## Dataset
  <p> The dataset we used was from Kaggle Fake News dataset </p>
  <b> Link: https://www.kaggle.com/c/fake-news/data </b> <br/>

  ### Training
  <p> We  have  used  Kaggle fake news data to train our RCNN model. This dataset can be categorized into 2 classes namely reliable and unreliabele. We have shown word ccloud for one of the class. </p>
  <br/>
  <p align="center"> <img width=700 height= 350 src="https://github.com/waleedasghar/Fake-News-Detection/blob/main/images/word.jpg"> </p>

## Proposed Solution
The first step is to clean up the raw text data.  Several stop words needs to be removed e.g.  prepositions,mentions,  hashtags,  URLs,  etc.   After a cleanup,  the data needs  to  be  converted  in  vector  form  to  feed  to  a  DeepNeural Network.  For the word2vec conversion, skip grammodel  is  used. This  model  learns  the  vector  representation from the raw data using the similarity between severalwords  based  in  their  context. The  objective of the Skip-gram model is to learn word representations that are usefulfor predicting the nearby words in a document. Formally, given a sequence of training words/sentence, the objective of the Skip-gram model is to maximize the average log probability.

<p align="center"> <img src="https://github.com/waleedasghar/Fake-News-Detection/blob/main/images/method.png"> </p>

After the conversion of words to usable representation,the next step is to feed it to a classifier. RNN and LSTM are commonly used to extract the global information fromthe data.  RCNN on the other hand, maintains the local in-formation which signifies the prominent features within thelimited  context  of  the  document. In this way, an overall response  can  be  pooled  at  the  end  which  can  better  helpduring the classifications. In this model, we use a recurrent architecture, which is a bidirectional recurrent network, to capture the contexts. The recurrent structure can obtain all context in a forward scan of the text and context in a backward scan of the text. After we obtain the representation of the word, we pass it to the Max-pool layer which gets the most dominant features which are then passed to the FC layer to get classified.

## Training Setup
We used this LSTM, Bi-LSTM and RCNN to train on dataset which had two class i.e. reliable and unreliable news.

Following configurations were used for final model training.
  - Batch Size: 64
  - Embedding Dimension: 300
  - Embedding Layers: 2
  - Embedding Layers size: 100
  - Learning rate: 0.5, 0.005 and 0.0005
  - Optimizer: SGD
  - Loss: Cross Entropy

  ### Experiments
   - Experiment 1: Performed on LSTM
      - Learning rate 0.005
      - Learning rate 0.0005
   - Experiment 2 Performed on Bi-Directional LSTM
      - Learning rate 0.005
      - Learning rate 0.0005
   - Experiment 3 Performed on RCNN
      - Learning rate 0.05
      - Learning rate 0.005

## Results
<p align="center"> <img src="https://github.com/waleedasghar/Fake-News-Detection/blob/main/images/table1.png"> </p>
<p align="center"> <img src="https://github.com/waleedasghar/Fake-News-Detection/blob/main/images/table2.png"> </p>
<p align="center"> <img src="https://github.com/waleedasghar/Fake-News-Detection/blob/main/images/table3.png"> </p>

## Analysis
<p align="center" height=300 width=300> <img src="https://github.com/waleedasghar/Fake-News-Detection/blob/main/images/acc.png"> </p>
</br>
<p align="center" height=300 width=300> <img src="https://github.com/waleedasghar/Fake-News-Detection/blob/main/images/lstm.png"> </p>

## Reference

  - RCNN model class: https://github.com/AnubhavGupta3377/Text-Classification-Models-Pytorch/tree/master/Model_RCNN

