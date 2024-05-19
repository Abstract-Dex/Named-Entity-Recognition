# Named Entity Recognition

Named Entity Recognition (NER) is a subtask of information extraction that locates and classifies named entities mentioned in unstructured text into pre-defined categories such as the person names, organizations, locations, etc.

This task is done with the help of the Hugginface libraries: `transformers` and `datasets`

## Dataset

The dataset used for this task is the `CoNLL-2003` dataset which is available in the `datasets` library. The dataset is already split into training, validation, and test sets.

### Data description

- id: a string feature.
- tokens: a list of string features.
- pos_tags: a list of classification labels (int).
- chunk_tags: a list of classification labels (int).
- ner_tags: a list of classification labels (int). Full tagset with indices:

## Model

The model used to perform the NER task is the `BertForTokenClassification` model which is a BERT model pre-trained for token-level classification tasks. The model can be found [here](https://huggingface.co/google-bert/bert-base-uncased).

This model is then fine-tuned on the `CoNLL-2003` dataset.

## Training

The model is trained using the `Trainer` class from the `transformers` library. The training is done on the `CoNLL-2003` dataset with the following hyperparameters:

- `batch_size`: 16

- `learning_rate`: 2e-5

- `epochs`: 3
