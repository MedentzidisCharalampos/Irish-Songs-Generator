# Irish-Songs-Generator
The data is inserted via the irish-lyrics-eof.txt text file and is splited into sequences.  
A Python List of sequences(the corpus) from the data is created and is converted to lowercase.    
The dictionary of words is created from corpus using the tokenizer, this is a key-value pair with key being the word and the value being the token for that word.     

For each line in the corpus we generate a token list using the tokenizers, this will convert a line of text like "In the town of Athy one Jeremy Lanigan" into a list of the tokens [4 2 66 8 67 68 69 70] representing the words.    
We iterate over the list of tokens and create a number of n-grams sequences.  
Line                       
 [4 2 66 8 67 68 69 70]          
Input Sequences    
 [4 2]                                                     
 [4 2 66]   
 [4 2 66 8]          
 [4 2 66 8 67]          
 [4 2 66 8 67 68]  
 [4 2 66 8 67 68 69]  
 [4 2 66 8 67 68 69 70]       
 
 The input sequences are simply the sentences being broken down into phrases the first two words, the first three words e.t.c.  
 We find the length of the longest sentence in the corpus and pad all of the sequences so that they are the same length.  
 We pre-pad with zeros so that it is easier to extract the label.  
 
 Input Paddded Sequences    
 [0 0 0 0 0 0 0 4 2]                                                     
 [0 0 0 0 0 0 4 2 66]   
 [0 0 0 0 0 4 2 66 8]          
 [0 0 0 0 4 2 66 8 67]          
 [0 0 4 2 66 8 67 68]  
 [0 4 2 66 8 67 68 69]  
 [4 2 66 8 67 68 69 70]  
 
 The next thing is to turn sequencies into x's and y's, the input values and their labels. All but the last character is the x and the last characted is the y. Then the labels will be one-hot encoded as this is a classification problem.  
 
 The architecture of our model is as follows:  
 1. An Embedding Layer thats embeds the total of words in the dimension 100  
 2. A Long Short Term Memort Biderectional Layer with 150-units  
 3. A Dense Layer for the total number of words and Softmax activation function  
 
 The model is compiled with categoricalCrossentropy as loss function and Adam as optimizer with learning rate 0.01 .  
 The model is trained for 100 epochs because there is not a lot of data.  

















