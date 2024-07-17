word level language model: 

- they have 17000 words

- each word is asociated with a 30 dimensional feature vector i.e **every word is embedded into a 30 dimensional space**
    - each word will have 30 dims so we will have 30 neurons per word

    - in the beginning the words(embedding) are initialized randomly, they are spread out at random

    - we will tune these embeddings using backpropagation

- during the training of the NN, these vectors will move around in this space and words which are similar will end up in the similar part of the space, so **they will be closer**

Layers -
1. the input layer - we have 17k words but in the paper we are taking the example of only three words

2. hidden layer (the tanh layer) - we can define how many neurons we want in this layer, change it later i.e with hyperparameter tuning
    - the neurons in this layer are fully connected with the neurons in the words, 90 neurons(30 neurons per word * 3 words)


3. softmax - it has 17k neurons and all of them are FC to the neurons in the hidden layer making it a very expensive computation

Output of the NN:

probability of the next word given the current words

Goal:

During training we have the label, the next word in the sequence, we can use the index of that word to get the prob of that word, so we will maximise the prob of that word w.r.t the parameters of this NN!

Parameters: 

- w, b of the output layer
- w, b of the hidden layer
- embedding lookup table

we will optimize these parameters using backprop
