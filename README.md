# Generative AI with LSTM - Text Generation

## Project Overview

This project implements a text generation system using a Long Short-Term Memory (LSTM) neural network with TensorFlow/Keras.

The model learns patterns from a large text dataset and generates new text by predicting the next word based on a sequence of previous words.

## Dataset

The project uses the following text dataset:

`Harry_Potter_all_char_separated.txt`

The dataset is included in this repository and is used for training the next-word prediction model.

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Google Colab

## Model Architecture

The LSTM text generation model consists of:

1. Embedding Layer
2. LSTM Layer
3. Dense Output Layer with Softmax activation

### Model Configuration

- Vocabulary Size: 10,000
- Sequence Length: 20
- Embedding Dimension: 128
- LSTM Units: 128
- Optimizer: Adam
- Loss Function: Sparse Categorical Crossentropy
- Batch Size: 256
- Epochs: 3

## Data Preprocessing

The text dataset is preprocessed using the following steps:

1. Convert the text to lowercase.
2. Remove punctuation.
3. Replace special separators with spaces.
4. Normalize whitespace.
5. Tokenize the text into words.
6. Convert words into numerical token IDs.
7. Create input-output sequences.
8. Use the previous 20 tokens as input.
9. Use the next token as the target output.

## Input and Output Preparation

For next-word prediction, sequences of 21 tokens are created.

- First 20 tokens are used as the input sequence.
- The 21st token is used as the output/target.

The dataset is divided into:

- 90% Training Data
- 10% Validation Data

## Model Training

The model is trained using the Adam optimizer and Sparse Categorical Crossentropy loss.

Early stopping is implemented using validation loss to help prevent overfitting.

## Text Generation

After training, the model generates new text from a seed sequence.

The generation process works as follows:

1. Take a seed sequence as input.
2. Convert the seed text into token IDs.
3. Use the last 20 tokens as the model input.
4. Predict the probability of the next token.
5. Select the next token using temperature-based sampling.
6. Convert the predicted token back into a word.
7. Add the word to the generated text.
8. Repeat the process to generate additional words.

## Sample Seed Inputs

The model was tested using multiple seed sequences, including:

- `harry looked at`
- `the professor said`
- `hermione walked into`
- `ron looked around`
- `the door opened`

The generated results are available in:

`generated_samples.txt`

## Creativity / Hyperparameter Experiment

Different temperature values were used during text generation to experiment with the randomness and diversity of the generated text.

The following temperature values were tested:

- 0.5
- 0.8
- 1.0

A lower temperature produces more predictable output, while a higher temperature allows more diverse and random word selection.

Multiple seed sequences were also tested to observe how different starting contexts affect the generated text.

## Project Files

- `Harry_Potter_all_char_separated.txt` - Text dataset used for training
- `lstm_text_generation.ipynb` - Complete implementation of preprocessing, model building, training, and text generation
- `generated_samples.txt` - Generated text samples from multiple seed sequences
- `README.md` - Project documentation
- `requirements.txt` - Required Python libraries

## How to Run

### Using Google Colab

1. Open `lstm_text_generation.ipynb`.
2. Upload `Harry_Potter_all_char_separated.txt`.
3. Run the notebook cells in order.
4. The dataset will be preprocessed and tokenized.
5. Input-output sequences will be created.
6. The LSTM model will be built and trained.
7. Text will be generated using different seed sequences.
8. Generated samples will be saved to `generated_samples.txt`.

## Results

The trained LSTM model successfully generates new text based on different seed inputs.

The generated text demonstrates the model's ability to learn word-level patterns from the training dataset and predict subsequent words iteratively.

Sample outputs from multiple seed sequences are provided in:

`generated_samples.txt`

## Conclusion

This project demonstrates a complete LSTM-based text generation pipeline, including text preprocessing, tokenization, input-output sequence preparation, model development, training, validation, early stopping, and iterative text generation.

The project also includes a temperature-based generation experiment to explore the effect of hyperparameters on generated text diversity.

## Author

Utpal Patel
