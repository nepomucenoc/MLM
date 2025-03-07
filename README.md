# BERT Masked Language Modeling (MLM)

This repository demonstrates how to use the **BERT** model for **Masked Language Modeling (MLM)**. The code utilizes the pre-trained **BERT** model (`bert-base-uncased`) from Hugging Face's `transformers` library to predict missing words (represented by the `[MASK]` token) in a given sentence.

## What is Masked Language Modeling (MLM)?

**Masked Language Modeling (MLM)** is a pretraining objective for models like **BERT**. In this task, certain words in a sentence are replaced with a special token (e.g., `[MASK]`), and the model is trained to predict the original word that should go in place of the `[MASK]`. Unlike traditional left-to-right or right-to-left models, BERT can consider both the left and right context of a word because it is bidirectional, making it more powerful in understanding the context of a given word.

MLM is used during BERT's pretraining phase to teach the model how to learn contextualized representations of words.

## Code Explanation

### Dependencies

The code requires the following Python libraries:

- `transformers` by Hugging Face
- `torch` (PyTorch)

You can install the dependencies using `pip`:

```bash
pip install transformers torch```

### Code Overview
1. Load Pre-trained BERT Model and Tokenizer: We load the pre-trained bert-base-uncased model and its tokenizer from Hugging Face. The model is pre-trained for MLM, so it can predict masked words in a sentence.

2. Prepare Input Text: We provide a sentence with a word replaced by the [MASK] token. For example:
```python
text = "The quick brown fox jumps over the [MASK] dog."

3. Tokenization: The input text is tokenized into tokens that the BERT model can understand. The tokenizer converts the [MASK] token into its corresponding token ID.

4. Model Prediction: The tokenized input is passed through the BERT model. The model generates logits (predictions) for each token in the sequence. We focus on the prediction for the [MASK] token.

5. Post-processing: The token with the highest logit is selected as the predicted word for the [MASK] token. We then decode this predicted token back into a word.

6. Replace [MASK] with Predicted Word: Finally, the original text is updated by replacing the [MASK] token with the predicted word.

## Model Runtime Information
The model took approximately 9 hours, 44 minutes, and 50 seconds (9:44:50) to run and make the predictions. This time includes the processing and prediction steps for the given input sentence.
![WhatsApp Image 2025-03-06 at 20 54 51_918690a5](https://github.com/user-attachments/assets/3ff64a4f-4881-4437-aa2d-f2dcc8a6e44b)

## Conclusion
This code demonstrates the core functionality of Masked Language Modeling (MLM) using the pre-trained BERT model. MLM is a key component of BERT's pretraining process, allowing the model to learn contextual relationships between words. This technique is not only useful for pretraining models but can also be applied in real-world NLP tasks such as text completion, question answering, and text understanding.

