# Trump v.s. Hilary LSTM

## Simple RNN/LSTM implementation for classification problem given political twitter texts

The 2016 Presidential Election certainly provided an interesting and shocking events for people all around the world.
During the process Social Media such as Facebook and Twitter played an important role. This notebook attempts to use a simple
RNN / LSTM model for predicting whether a certain tweet was from Trump or Hilary during the 2016 Election Period. Credits to training
data goes to *Hilary Clinton and Donald Trump Tweets* Dataset on kaggle. A total of 9K tweets were preprocessed and fed to the LSTM model
for classification problem.

### Data Preprocessing
Only original tweets (excluding retweets by other users) from either Hilary Clinton or Donal Trump were used. Any url link to an article or image were removed using regex. Keras's Tokenizer was used to pick 3000 top words in the tweets and turned as a sequence data.

### Model Building
An embedding layer followed by a single LSTM layer was used for the RNN model. After the LSTM layers a Dense layer with 2 output nodes were put on top for binary classification. The model was not fined tuned as this was only my first attempt for classification.

### Results
The model was trained for 32 epochs and finished training with almost 100% training accuracy and almost 92% validatoin accuracy. Quite promising results considering that this was my very first attempt at this classification problem.

### Evaludation of the results
At first, 92% validation accuracy seemed to be way too optimistic as a first attempt. So, in order to evaludate the model. As a quick test, I searched for most recent tweets from both Hilary and Trump and used the trained RNN model to predict the text's author. Yet again, the model seemed to provide the correct labels for each of the tweets.
What are some possible factors that could have influenced such high accuracy rate then? Firstly, Trump is known for his selected range of vocabulary such as "the wall", "great", "extremely", "tremendous" and etc. The stark difference between sets of vocabularies that Trump and Hilary use could have helped the RNN to easily make the distinction. Secondly, looking at the data, we can clearly see that Trump uses far more capitalization to emphasize his points compared to Hilary who barely uses them at all. This could have been another reason to why RNN had an easy time classifying author of the texts.

For a full functioning example, please look at the Colab Note bok on:
https://drive.google.com/open?id=1cevfCUmqTPTF6Tqz84dctf65wi0kEzDb

Or directly visit Jupyter notebook on this repository:
https://github.com/RE-N-Y/Trump-v.s.-Hilary-LSTM/blob/master/Trump%20vs%20Hilary.ipynb
