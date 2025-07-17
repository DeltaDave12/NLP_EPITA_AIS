## NLP Graded Project 
Important : This file contains the part 4 requirements of the NLP assignement as well as an overall description this NLP practice

## Members:
David ROSSIG

An Huy PHAM

### Goal
The goal of this assignement is to expirement with different NLP related models, in the context of emotion classification.

### Dataset
The dataset consist of a list of tweets with emotion labels. Data is available in "data" folder (txt format). 
Columns : 

- sentence : a sequence of words (ex : ive been feeling a little burdened lately wasnt sure why that was)
- label : emotion that is either surprise / love / fear / anger / sadness / joy

### Models

- [FCNN](./src/notebooks/fcnn.ipynb) : Fully-connected neural network
- [LSTM](./src/notebooks/lstm.ipynb) : Recurrent Neural Network based on LSTM
- [Transformer](./src/notebooks/transformer.ipynb) : Fine-tuning of the distilbert-base-uncased model (through the huggingface transformers library and pipeline)

### Results 

We decided to focus on the Macro Average (given by SKlearn classification report metrics) :

| Model       | Macro Precision | Macro Recall | Macro F1 |
|-------------|----------------|--------------|----------|
| FCNN        | 0.59           | 0.47         | 0.49     |
| LSTM        | 0.53           | 0.45         | 0.45     |
| Transformer | 0.87           | 0.88         | 0.88     |

- FCNN performance can be explained since it is the simplest model here by far, despite fast training time. It cannot capture relathionships or context in the Tweets
- LSTM model average performance, even though on paper it should be better than FCNN, can be explain due to the dataset size being too small, meaning it didn't have enough time to learn the context of the tweets and also due to its black box nature.
- Transformer has nice performance, since we saw in class that this model is game changing for the NLP field and doesn't need to process the tweets in specific order(see [Other text classification use case](#other-text-classification-use-case) section)

### What we have learned 

- Developp NLP through AI
- Expiriment with different SOTA models for a specific task
- Classifiy emotions in a social media context
- Lerning how to implement and discover AI related python libraries : torch, spacy, huggingface...
- Critical thinking in the field of NLP

### Other text classification use case 

Let's take another use case : classifiying e-commerce websites. We can go from this [dataset](https://www.kaggle.com/datasets/saurabhshahane/ecommerce-text-classification). Based on our work regarding emotion classification, we would use a Transformer model for this task : the model provides flexibility (fine-tuning), handles relathionships between words very well and their ressource-hungry nature is countered by it's attention mechanism, giving it very good performance and accuracy.
