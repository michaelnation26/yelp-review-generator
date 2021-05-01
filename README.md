# Yelp Review Generator

A seq2seq (BERT) model from HuggingFace was trained on the [Yelp Open Dataset](https://www.yelp.com/dataset) to generate Yelp reviews.

#### Dataset

- ~1.5M reviews (subset of the ~8M reviews from [Yelp Open Dataset](https://www.yelp.com/dataset))
- ~100k businesses

#### Model Input Features

- stars: rating of business (1 - 5)
- funny: number of funny votes received
- elite level: total number of years the reviewer was elite
- name: business' name
- city: city of the business
- categories: business categories

The six input features are concatenated into a single string for each example.

#### Model Output (label)

- Yelp review

During training, the Yelp review is constrained to 128 tokens. During inference, the model can generate words until an EOS token is generated or stopped early at a predetermined fixed length.

## Getting Started

#### Training the Model

To train a new model, use the [seq2seq_train notebook](https://drive.google.com/file/d/1BsMFZBG7QhGyXBTO-8BWQRkX4gqcJ7Cb/view?usp=sharing). The [Yelp Open Dataset](https://www.yelp.com/dataset) needs to be downloaded first.

#### Generate Reviews with Trained Model

Use the [seq2seq_predict notebook](https://drive.google.com/file/d/1rjJYoIJsgnnN_tkYV00MQ5fh3sf9a6Sm/view?usp=sharing). The model trained from this project will be downloaded automatically in the notebook. You don't have to provide your own trained model.
