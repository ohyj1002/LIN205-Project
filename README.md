# LIN205-Project (Yoo Jung Erika Oh)
This is a repository for LIN205 project.

This project was designed to build text classifiers.

<b>Introduction and task description</b>

The aim of this task is threefold.
The first goal of the study is building a text classifier that can successfully categorize human commmunication processes into the predefined categories. This task is based on Bales'(1950) theoretical framework on coding communication/interaction processes. Originally, there are a total of 12 categories (ranging from "showing solidarity" to "showing antagonism"). These 12 categories can be simplified into 3 categories: Positive sociomotional area, Task (neutral) area, and Negative socioemotional area. 

Second goal of this task is to train, test, and compare the performance of two classifiers, Naive Bayes and Recurrent Neural Network - Long Short Term Memory (RNN-LSTM). In this study, Naive Bayes model, which is a simple but powerful tool for text classification, is used as a baseline classifier. Starting from that, RNN model is used for comparison. Especially, I use a special form of RNN, which is called Long Short Term Memory Network (LSTM). LSTM is especially powerful when it comes to finding the right features when the chain of input-chunks becomes longer. Since the dataset contained some long text inputs, I expected that it would perform well in this particular task.

Last goal of this task is comparing two different types of word embedding models in the RNN-LSTM model. In particular, I compare pretrained GloVe word embedding with custom word embedding which I trained with my dataset. This is to see whether custom word embedding would perform better since the semantic relationship of my own training corpus can be better represented.


<b>Data description</b>

For this project, I used two datasets which came from different tasks.

<i>Dataset1: Persuasion task dataset</i>

Two people were randomly assigned to an online chatroom where one person was asked to persuase the other person to donate to a children's charity (called "Save The Children"). At the end of the task, participants had to indicate their amount of donation. Also, they were asked to chat for at least 10 turns.

<i>Dataset2: Advice-giving task dataset</i>

Two people were randomly assigned to an online chatroom where one person was asked to give sleep-related health advice to the other person. In particular, they were given one of two advices (1. do not use electronic devices before bed, 2. establish a wind-down routine before bed). They were encouraged to chat at least for 10 turns.

A total of 1427 example texts (lines) were used in the training dataset.


<b>Model description (detailed descriptions are provided in each python notebook files)</b>

<i>Naive Bayes Model (Baseline)</i>

Removed stopwords

Used Laplace smoothing

Split 80% training, 20% testing 


<i>RNN-LSTM Models</i>

Model structure:

Embedding layer (100 dimensions)

LSTM layer (100 units)

Dense layer

Used early stopping to avoid overfitting

Split 80% training, 20% testing


<b>Results (detailed comparions are provided in the presentation slide file)</b>

Overall, RNN-LSTM models performed better than Naive Bayes model. In particular, Naive Bayes model had low f1-scores (less than .5) for two categories (negative socioemotional and task-focused) because it could not distiguish negative / non-task focused utterances due to unbalanced nature of the dataset. However, RNN-LSTM models reached a fairly good f1-scores (above .8) for task-focused category. This is an improvement from the baseline model. However, the negative socioemotional cateogory was still unresolved for RNN-LSTM models. 

Generally, pre-trained Glove embeddding and custom embeddings showed similar performance, but custom embedding performed slightly better. 


<b>Discussion</b>

In the study, it was discovered that even with small training dataset, RNN-LSTM models outperformed the baseline mode (Naive Bayes). Yet, one category (negative socioemotional) still remained unresolved. This may have been due to not only the highly unbalanced dataset (there were very few cases of negative socioemotional utterances), but also the subtle nature of those negative socioemotional utterances. Therefore, in future studies, it would be crucial to increase the size of the training dataset and also use different datasets where negative socioemotional utterances are more explicit.  


<b>REFERENCES</b>

Bales, R. F. (1950). Interaction process analysis; a method for the study of small groups.
