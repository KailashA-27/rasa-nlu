# rasa-nlu

I developed this project on Anaconda by writing shell commands. You first need to init rasa by using the following command: python -m rasa init .
I start a new spaCy project that contains my custom entity detection model. I used the ner demo starterpack from spaCy so that I can get started quickly.

Then I entered the following command :

python -m spacy project clone pipelines/ner_demo_replace
cd ner_demo_replace

The ner_demo_replace package contains a spaCy project that is used to train an entity detection model.

python -m spacy project run 
This command is used to run the spacy project.

Creating a new model and then packaging it up. So I'll run the all command first using : python -m spacy project run all
This will convert the training data to a binary format, configure, train and evaluate the trained model. Once that is done I'll package it with the package command: python -m spacy project run package
I've exported a setup.py file here as well. I means that I can install the trained spaCy model via pip to have it available in my virtual environment.

Then I've used this command to install the packages:
python -m pip install packages/en_ner_demo_replace-0.0.0/

Now that the model is installed and I can access it from spaCy within python too. It's load-able via the spacy.load command.
Then I made changes to config.yml file.
These changes can be viewd in the respective file.

I added the training data to the nlu.yml files.

I trained the model using shell command:
rasa train nlu

Once the training is done I used the command:
rasa shell nlu 

Then you can type the respective sentences from Task 1 in the Anaconda command prompt. It identifies the intent and entity clearly in a JSON format.


Details about Task 1:-

- The Audio file from the given link in Task 1 was downloaded. I've used Amazon Web Services-Audio Transcribe for Speech-to-text conversion.
- The auido file was uploaded on S3 bucket, from where it was sent to AWS Audio Transcriber for text extraction.
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

- The call was made by Mike to Nancy regarding updating product prepaid connection to new postpaid connection. Nancy agreed to this.

 
