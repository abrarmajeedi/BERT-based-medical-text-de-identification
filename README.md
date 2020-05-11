# BERT based medical text de-identification

## Requirements:
We have used the Transformers library of python. 
The pretrained BERT model we have used is SciBERT which was trained on scientific corpora. 
The model will be automatically downloaded when you run the code for the first time.

## How to reproduce the results / train your own BERT based de-identificatiion model for a different dataset
Download the MIMIC III dataset. Extract the "NOTEEVENTS.csv" file

Run Preprocessing notebook to preprocess the data. 
Then run De-identification NB to train a SciBERT model for de-identification.

## Note: 
We used only 500 million character subset of the full dataset. You can run it for the full dataset by just changing the splicing indices in the Preprocessing notebook. Since the MIMIC-III dataset provides no annotation, we have re-identified the data by filling in realistic looking fake date.

## Train test split:
We train on 75% of data and test on 25%

## Results:
|    Class              |    Positive Predictive Value   (Precision)    |    Sensitivity (Recall)    |    F1-score      |
|-----------------------|-----------------------------------------------|----------------------------|------------------|
|    CONTACT            |    0.98336516                                 |    0.98241133              |    0.98288801    |
|    DATE               |    0.99244865                                 |    0.99275729              |    0.99260295    |
|    LOCATION           |    0.99569739                                 |    0.99507795              |    0.99538757    |
|    NAME               |    0.99179696                                 |    0.99013438              |    0.99096497    |
|    OTHER (non-PHI)    |    0.99934905                                 |    0.99934959              |    0.99934932    |
|    UNIQUE ID          |    0.96716848                                 |    0.97340426              |    0.97027635    |


### Credits:
The [tutorial](https://www.depends-on-the-definition.com/named-entity-recognition-with-bert/) by Tobias Sterbak was very helpful for training the BERT model




