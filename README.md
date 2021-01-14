# Chatbot
Chatbot: Building a Seq2Seq Model using Attention Mechanism

## Data
Cornell Movie dataset:
This corpus contains a large metadata-rich collection of fictional conversations extracted from raw movie scripts and is sufficiently large for training.
https://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html
Next:
We are going to use Cornell movie dialogs data for our project because it is publicly available and is sufficiently large. This corpus contains a large metadata-rich collection of fictional conversations extracted from raw movie scripts. 220,579 conversational exchanges between 10,292 pairs of movie characters.

## Approach:
Step 1: Data Preprocessing:
● Splitting and cleaning the text (ex I’m to I am)
● Split and store questions and replies separately
● Filtering out the required length of conversations using minimum & maximum threshold
● Selection of records as training on whole data is computationally expensive
● Tokenizing data
● Splitting into train-test
● Build vocabulary
● Remove rare words using min frequency
● Padding of sentences
Step 2: Model Building
● Little research on Seq2Seq Model with and without attention mechanism
Seq2Seq Model without attention: (Encoder - Decoder Model)
● a sequence to sequence model aims to map a fixed-length input with a fixed-length output where the length of the input and output may differ.

Limitations:
● Long Sequences: By using a fixed dimensionality vector for encoding the whole input sequence is not capable of capturing the whole information.
In the case of long sequences, there is a high probability that the initial context has been lost by the end of the sequence.

To overcome the limitation of the encoder-decoder model, Attention Mechanism was introduced in the Seq2Seq Model.

Step 3: Model Running
● For training a sample of 1k samples using Google Colab GPU took about 5 hours to run.
● Researched about different GPU Options and finally chose Floyd Hub GPU services to train our model.
● Final model is trained on 100k samples and the total time taken to train the model is 4 hours using Floyd Hub GPU services.
Step 4: Hyper parameter tuning
● Referred various articles to choose the best hyper parameters for the Seq2Seq Model.
Embedding Size: 128, Hidden states in each LSTM: 512, optimizer: Adam
Loss: Binary Cross entropy, Batch size: 64, Number of epochs: 100

Step 5:Model Evaluation
● Used Bleu score to compare the context of the output with the actual answer.

G. Summary:
After selecting the data source, we checked multiple research papers on chatbot and decided
to implement Seq2Seq with Attention as it had relatively easier implementation and provided
good results. We started with data exploration to find the data quality and issues. We then performed
Data cleaning and preprocessing for passing it on to the model. Building, debugging and testing
the model was time consuming task. Since we had tried with only a small sample of data while
Developing the model, the next challenge was model training for the bigger sample. We had read
and tried out different cloud services and finally chose to work with Floyd Hub as it provided good
GPU’s at a reasonable price. We managed to pick the right hyper parameters after much
trial and error.

