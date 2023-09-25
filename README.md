# Chatbot-SYNC-interns
chatbot model using chatterbot dataset from kaggle and a LSTM based model

Project walkthrough:

1- I started with loading my data and making sure questions and answers lists contain nothing but strings for my tokenization in the second step. The answers list had 2 dictionaries which threw an error and it is commented in the code why I manipulated the answers list that way replacing 2 instances with strings.

2- Tokenziation of questions and answers to get the full vocab then applying tokenization ,test to sequence, on each seperatly and padding them to the max length of questions and answers respectively.

3- Creating the model I used LSTMs of 256 units and also embeddings of both questions and answers of 256 as they have to have the same shape at the end the decoder outputs are passed to a Dense layer with softmax activation and a number of units the same as the number of available vocabulary so that the model generates the words.

4- The model archeticutre is pretty simple the encoder inputs are the questions tokenized and padded while the decoder inputs are the states (h, c) from the encoder output and the answers tokenized and padded. It was trained won the whole data without testing as I did not split the data however when testing make sure to take a portion of each file so that the testing data is balanced with the content of the training data as the model might test in a category it has never been trained on affecting the accuracy drastically.

5- Finally, an inference function to provide the encoder model and decoder model at run time and the preprocessing of the user input.
