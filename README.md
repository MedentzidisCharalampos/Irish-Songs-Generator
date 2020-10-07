# Irish-Songs-Generator
The data is inserted via the irish-lyrics-eof.txt text file and is splited into sequences.  
A Python List of sequences(the corpus) from the data is created and is converted to lowercase.    
The dictionary of words is created from corpus using the tokenizer, this is a key-value pair with key being the word and the value being the token for that word.     

For each line in the corpus we generate a token list using the tokenizers, this will convert a line of text like "In the town of Athy one Jeremy Lanigan" into a list of the tokens [4 2 66 8 67 68 69 70] representing the words.    
We iterate over the list of tokens and create a number of n-grams sequences.  
Line                       
 [4 2 66 8 67 68 69 70]          
Input Sequences    
 [4 2 ]                                                     
 [4 2 66]   
 [4 2 66 8]          
 [4 2 66 8 67]          
 [4 2 66 8 67 68]  
 [4 2 66 8 67 68 69]  
 [4 2 66 8 67 68 69 70]          



















We create an Irish song  based in a known song. This is a multi-class classifier, as every prediction is one of the classes. The number of classes equals to the size of the dictionary.
