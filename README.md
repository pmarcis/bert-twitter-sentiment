## Latvian Twitter Sentiment
Repository for the paper **Pretraining and Fine-Tuning Strategies for Sentiment Analysis of Latvian Tweets**.
Performs 3 class(Positive, Negative and Neutral) classification on Latvian tweets. The model is trained in tweets from the domain of politics.

### Data
- Latvian Tweet Corpus. Since the twitter data cannot be shared directly due to twitter terms, kindly refer https://github.com/pmarcis/latvian-tweet-corpus for the data.

### How to run
- #### Train
  - Pre-training - run.sh present bert-twitter-language-pretraining/ folder. Update the paths to the train and eval split.
    - mBERT https://github.com/huggingface/transformers/blob/master/examples/language-modeling/
    - For pretraining ALBERT and ELECTRA https://github.com/shoarora/lmtuners/tree/master/experiments/disc_lm_small
  - Fine-tuning  `cd bert-sentiment/src;python train.py` 
    - Update the config.py file with the pretrained models link 
    - Update train.py for the locations of the dataset
    - train.py expects pre-processed and pre-split data files( train, dev, test)
- #### Predict
  - To perform a prediction on file, create a csv file with tweets with header **text** and  **label**. The label column is blank.
  - `python predict.py --test_file  --model_path `. where ignore the model_path flag if it is set in config.py. Pass the test_file created in previous step.

- #### DEMO
 -`python app.py`

### Performance Metrices
Accuracy score of around 76% on time-balanced dataset.

### Publication
Gaurish Thakkar and  Mārcis Pinnis. (2020). [Pretraining and Fine-Tuning Strategies for Sentiment Analysis of Latvian Tweets](http://ebooks.iospress.nl/volumearticle/55523). In Human Language Technologies – The Baltic Perspective - Proceedings of the Ninth International Conference Baltic HLT 2020. 55-61. IOS Press.

#### BibTeX
```bibtex
@inproceedings{Bergmanis2020,
  address = {Kaunas, Lithuania},
  author = {Thakkar, Gaurish and Pinnis, M\=arcis},
  booktitle = {Human Language Technologies – The Baltic Perspective - Proceedings of the Ninth International Conference Baltic HLT 2020},
  doi = {10.3233/FAIA200602},
  pages = {55--61},
  publisher = {IOS Press},
  title = {{Pretraining and Fine-Tuning Strategies for Sentiment Analysis of Latvian Tweets}},
  year = {2020}
}
```

### Acknowledgement
The project has received funding from the European Union’s Horizon 2020 research and innovation programme under the Marie Skłodowska-Curie grant agreement no. 812997.

### This work was done as a part of internship at [TILDE](www.tilde.com).
