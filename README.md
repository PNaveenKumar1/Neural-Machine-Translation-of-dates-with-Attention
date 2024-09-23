# Date Translation Using Attention Mechanism

## Overview
This project implements a neural machine translation model using an attention mechanism to convert human-readable dates into machine-readable format. We utilize Bahdanau's and Luong's attention mechanisms in conjunction with a bidirectional GRU-based encoder and GRU-based decoder to achieve this translation.

## Dataset
- **Training Set:** The training data consists of 36,000 examples and is provided in the file `Assignment2_train.txt`.
- **Validation Set:** The validation data is used to evaluate the model's performance and is stored in `Assignment2_validation.txt`.

Examples of input-output pairs:
- **Input:** "Saturday 29 February 2021"  
  **Output:** "2021-02-29"

- **Input:** "29 February 2020"  
  **Output:** "2020-02-29"

## Model Architecture
### Encoder
- The encoder is a bidirectional GRU that processes the input sequence and produces hidden states.

### Decoder
- The decoder is also a GRU, which takes in the encoded context from the encoder and generates the output sequence (machine-readable date).
- The decoder is coupled with the attention mechanism to focus on relevant parts of the input while generating the output.

### Attention Mechanism
- We implement **Bahdanau’s Attention** and **Luong’s Attention**. The attention mechanism computes weights for each input token, guiding the decoder to focus on important parts of the input date during translation.
- The attention weights are visualized for specific examples, showing which parts of the input contribute to each output token.

## Training
- **Loss Function:**  Cross-Entropy
- **Optimizer:** Adam Optimizer
- **Batch Size:** 32
- **Epochs:** 3

## Results
The model was evaluated on the validation set, and performance metrics such as accuracy and attention visualizations for specific date translations were generated.

- **Exact Matches:** 3,842
- **Less than 10 Error Matches:** 3

### Error Analysis:
- **Exact Match Error(No of dates macthes 10 digits exactly)**: 96.05%
- **Mismatch Error:** 0.4975%
- **Highest Error(index where most of mismatches occur):** 2%
- **Lowest Error(index where less no of mismatches occur):** 5%

