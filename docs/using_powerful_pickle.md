# Using Powerful Pickle

## :cucumber: Introduction

Powerful Pickle is a script that applies machine-learning models to text data. Predictions can be helpful when trying to find something specific, and will hopefully make it easier to gather facts from large corpora.

## :hammer_and_wrench: How to

If Powerful Pickle is installed, it shows up as a classification script when using Dfi. Simply chose it as the classification step.

You will then be asked to select a model. Models - or more specifically _pipelines_ - are located at resources/Powerful_Pickle relative to the current working directory. Different pipelines will be trained with different data, and apply different processing steps to the text. Therefore, pipeline performance will vary, and will hopefully improve continuously as i explore more sophisticated ways to treat the data.

I will try to keep an updated record of the different models, giving some information about the training data, the different pre-processing steps, and some performance characteristics gained while training. This will hopefully give you a general idea of which models are the most helpful.

The output is, like before, a csv file, but with an additional “prediction”-column. The type of data in this column depends on the model used; currently i have implemented binary classifiers trained on evidence / non-evidence sentences related to ceasefires. With these models, a 1 in the prediction column will indicate that a sentence might be interesting for coding the starts of ceasefires. Again, refer to the specific model documentation for more information

## :computer: Models
- [Isaac_Brassard](./models/Isaac_Brassard.md)
