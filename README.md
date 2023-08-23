# gpt-llm-trainer
[![Twitter Follow](https://img.shields.io/twitter/follow/mattshumer_?style=social)](https://twitter.com/mattshumer_)

LLaMA 2 7B Fine-Tuning version: [![Open LLaMA Version In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1mV9sAY4QBKLmS58dpFGHgwCXQKRASR31?usp=sharing)

GPT-3.5 Fine-Tuning version: [![Open GPT-3.5 Version In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1NLqxHHCv3kFyw45t8k_CUfNlcepMdeDW?usp=sharing)

## Overview

Training models is hard. You have to collect a dataset, clean it, get it in the right format, select a model, write the training code and train it. And that's the best-case scenario.

The goal of this project is to explore an experimental new pipeline to train a high-performing task-specific model. We try to abstract away all the complexity, so it's as easy as possible to go from idea -> performant fully-trained model.

**Simply input a description of your task, and the system will generate a dataset from scratch, parse it into the right format, and fine-tune a LLaMA 2 or GPT-3.5 model for you.**

## Features

- **Dataset Generation**: Using GPT-4, `gpt-llm-trainer` will generate a variety of prompts and responses based on the provided use-case.

- **System Message Generation**: `gpt-llm-trainer` will generate an effective system prompt for your model.

- **Fine-Tuning**: After your dataset has been generated, the system will automatically split it into training and validation sets, fine-tune a model for you, and get it ready for inference.

## Setup
1. [Open the notebook in Google Colab](https://colab.research.google.com/drive/1mV9sAY4QBKLmS58dpFGHgwCXQKRASR31?usp=sharing) or in a local Jupyter notebook.

2. If you're using Colab, switch to the best GPU available (go to Runtime -> change runtime type).

3. Add your OpenAI API key to the line `openai.api_key = "YOUR KEY HERE"`.

## How to Use

1. Define your `prompt`. The `prompt` is a description of what you want the trained AI to do. The more descriptive and clear you can be, the better. Additionally, set the temperature we will use to generate your dataset (high=creative, low=precise), and the number of examples you want to generate (100 is a good starting point).

For example:
```
prompt = "A model that takes in a puzzle-like reasoning-heavy question in English, and responds with a well-reasoned, step-by-step thought out response in Spanish."
temperature = .4
number_of_examples = 100
```

2. Run all the cells (stop at `Merge the model and store in Google Drive` if using the LLaMA 2 version).

*It'll take some time (from 10 minutes to a couple of hours, depending on how many examples you generate), but soon, you'll have your fine-tuned model!*

3. After your model is trained, you can use the `Run Inference` cell (on the LLaMA 2 version) or the `Let's try it out!` cell (on the GPT-3.5 version) to test the model, and the cells below that allow you to save and load the model to and from Google Drive for later use if you are using the LLaMA version. If you're using the OpenAI version, your model will be available for use via the API or in the OpenAI Playground.

## Contributions are welcome! Some ideas:
- improve the example generation pipeline for efficiency/cost reduction (using n=)
- add additional example generation prompts to create more diverse examples
- add example pruning, removing very similar examples to improve performance
- use GPT-4 to automatically choose the training hyperparameters (and potentially, even the model to fine-tune!) based on a few examples + high-level dataset details (i.e. number of examples)
- train multiple model variants and choose the one with the lowest eval loss

## License

This project is [MIT](https://github.com/mshumer/gpt-llm-trainer/blob/master/LICENSE) licensed.

## Contact

Matt Shumer - [@mattshumer_](https://twitter.com/mattshumer_)

Project Link: [https://github.com/mshumer/gpt-llm-trainer](url)

Lastly, if you want to try something even cooler than this, sign up for [Personal Assistant](https://www.hyperwriteai.com/personal-assistant) (most of my time is spent on this). It's basically an AI that can operate your web browser to complete tasks for you.
