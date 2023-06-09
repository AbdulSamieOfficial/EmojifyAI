# EmojifyAI
EmojifyAI is a Python package that suggests relevant emojis for a given input sentence using natural language processing techniques. It employs the BERT model to generate embeddings for the input sentence and the emojis' descriptions, and then finds the most similar emojis using cosine similarity.

### Installation
To use EmojifyAI, you need to have the following libraries installed with Python 3.11:
  1. `transformers`
  2. `torch`
  3. `nltk`
  4. `numpy`
  5. `pandas`
  6. `re`
  7. `streamlit`

### Install Requirements
To install all the requirement of the project, simply type: 
`pip install -r requirements.txt`

#### You can install these dependencies using pip:
```pip install transformers torch nltk numpy pandas```

### Usage
Here's an example of how to use EmojifyAI:
```from EmojifyAI import EmojifyAI, suggestEmojis

emoji_rec = EmojifyAI()  # Instantiate the EmojifyAI class
emoji_rec.generate_emoji_csv()  # Generate the emoji data CSV file

mean_tokens = emoji_rec.process_csv()  # Process the CSV and obtain mean tokens for emojis
torch.save(mean_tokens, 'checkpoint/token-all.pt')  # Save the mean tokens to a file

test_sentence = "I am going to the movies"
suggestEmojis(test_sentence)  # Suggest emojis for the test sentence
```

### Emojify Class
The `EmojifyAI` class provides the following methods:
  1. `generate_emoji_csv()`: Generates an emoji data CSV file from the raw emoji data.
  2. `process_csv()`: Processes the emoji CSV file and calculates the mean tokens for the emojis' descriptions.
  3. `process_sentence(sentence: str)`: Processes the input sentence and returns the mean tokens for the sentence.
  4. `find_similarity(sentence_tokens, mean_tokens)`: Calculates the cosine similarity between the sentence tokens and the mean tokens of the emojis.
  
### SuggestEmojis function
The `suggestEmojis(sentence: str)` function is a helper function that takes an input sentence and suggests the most relevant emojis for the sentence. It uses the EmojifyAI class to process the sentence and find the most similar emojis based on the cosine similarity between the sentence and emojis' descriptions.  

### Run Code
There are two files in this project:
  1. To run `EmojifyAI.ipynb`, make sure to run it via Jupyter Noteebook.
  2. To run `EmojifyAI_SL.py`, type this command on terminal (directory), `streamlit run EmojifyAI_SL.py`.

### Output Demo
<img src="./Output/Output.gif" alt="Output Demo">


### Contributing
If you'd like to contribute to the project or report a bug, please open an issue or submit a pull request on the GitHub repository.

### Credits
  1. Abdul Samie
  2. Fatimah Noor

### License
This project is licensed under the MIT License.
