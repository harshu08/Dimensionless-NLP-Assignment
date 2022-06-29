# Dimensionless-NLP-Assignment


The project was developed on Anaconda platform using the shell commands and jupyter notebook. The project has two important modules/libraries.
1. RASA 3.2.1
2. Spacy 3.3.1 

The initial step is to start a new spacy project to contain the custom entity detection model. For this ner demo starterpack is used. The ner_demo_replace package contains a spaCy project that is used to train an entity detection model.

Next step is to create the model and package it. This command is used to run the spacy project: python -m spacy project run all. This will convert the training data to a binary format, configure, train and evaluate the trained model. Once that is done I'll package it with the package command: python -m spacy project run package

The trained spacy model can now be installed and imported in the enviroment. Now that our custom model is load-able by spaCy, it is also load-able from Rasa.

Next, a new rasa project is initialized. The changes have to made in th NLU pipeline using the 'config.yml' file to use our custom spacy model. The training data like name and product have been added to the file 'nlu.yml'. The rasa project is ready to be trained now.

Training of the the model is done using shell command:
rasa train nlu

Once the training is done, uhe rasa project is run using the command:
rasa shell nlu 

Then you can type the respective sentences from Task 1 in the Anaconda command prompt. It identifies the intent and entity clearly in a JSON format.

Details about Task 1:-

- The Audio file from the given link in Task 1 was downloaded. I've used Rev.ai for Speech-to-text conversion.
- The auido file was uploaded to the asr engine, from where the text extraction was done.
- The output was stored in a text file.

Details about Task 2:-

- For creating the NLU model, I used SpacyNLP pipeline for the extraction of names,products,etc.
- I used SpacyTokenizer for the process of tokenizing a text into segments of words and punctuation. It processes the text from left to right. 
- I then used RegexFeaturizer for creating a vector representation of user message using regular expressions.
- DIETClassifier was used to handle both intent classification and entity recognition together.
- RegexEntityExtractor was used to extract entities using the lookup tables for company names and person names in the training data.

Details about Task 3:-

- Each sentence form Task 1 was then supplied individually to the NLU model from which the model was able to correctly identify intro,purpose intents.
- The model was also able to extract entities like caller_name, company_name and their respective values from each sentence.
- The output given by the model was in JSON format which was saved.

Details about Task 4:-

- The call was made by Mike to Nancy regarding updating product prepaid connection to new postpaid connection. Nancy agreed to this. The information regarding this is in the JSON format found in the file 'output.json'.
