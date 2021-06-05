# Semantic_Text_Similarity_For_Short_And_Long_Text_Sequences


A lot of STS pre-trained models are available today, however there is one problem that almost all of them suffer from: They cannot handle very large inputs (for example, BERT has a limit of a maximum of 512 tokens) or lose out on important semantic information as the length of the input text increases (for example, the sentence encodings generated using Universal Sentence Encoder become less representative as the lnength of the input increases).


This notebook presents CNN+BiLSTM based Semantic Network for Semantic Similarity extraction from text input scalable to large text inputs.

The model takes as input a pair of sentences and outputs their Semantic Similarity Score.

We utilize pre-trained GloVe embeddings and generate a (sentence length, GloVe embedding length) matrix for each input sentence.

The two matrix generated for each input example (pair of sentences) are fed into the Siamese Network:

I: The CNN gathers some local context from neighboring words for each word to make the resultant embedding richer.

II: The 2 stacked BiLSTM are used to generate an ouput embedding representative of the entire sentence.

III: The L1 distance between these "sentence embeddings" is calculated and fed into a Fully connected layer that outputs the final similarity score.
