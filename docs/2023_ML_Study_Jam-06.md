# Encoder-Decoder Architecture

## Contexts

* [Course](#course)
* [TIL](#til)

## Course

* [x] VIDEO: Encoder-Decoder Architecture: Overview
* [x] VIDEO: Encoder-Decoder Architecture: Lab Walkthrough
* [ ] QUIZ: Encoder-Decoder Architecture: Quiz
* [ ] LINK: Encoder-Decoder Architecture: Lab Resources

## TIL

강의의 내용은 다음의 과정으로 전개됨.

* Encoder-Decoder Architecture: Overview
  * Encoder-Decoder Architecture
  * The training phase
  * The Serving phase
* Encoder-Decoder Architecture: Lab Walkthrough

### Encoder-Decoder Architecture

* Encoder(Encoding Stage): Unrolled recurrent neural network(RNN) - LSTM or GRU
* Decoder(Decoding Stage)

### Transformer History

* 1949 - 2001, Before ML era
* 2001, Natural Language Models
* 2008, Multi-task Learning
* 2013, Word2Vec and N-grams
* 2014, RNN/LSTM
* 2015, Attention mechanism
* 2017, Transformer <-- Large pre-trained language models
* 2018, BERT
* 2019, T5
* 2020, GPT-3
* 2022, PaLM
* 2023, GPT-4

### Lab Walkthrough

* ref: /asl-ml-immersion/notebooks/text-models/solutions/text_generation.ipynb
* purpose: to implement a character based text generator based on the encoder decoder architechture
* model: based on RNN(only trained for 30 epochs in the Vertex Air Workbench)
* loss: SparseCategoricalCrossentropy
  * task: classify next character
  * not directly the probability

  ```python
  batch_mean_loss = tf.losses.SparseCategoricalCrossentropy(from_logits=True)
  ```

* optimizer: Adam

encoder-decoder model can not to use immediately for inference. It needs to be used decoding function, decode generated text a step at a time using the trained model.

```python
## Notes of the wrong answers

(none)
