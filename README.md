# gpt-llm-trainer


## Overview
This is a fork of [gpt-llm-trainer](https://github.com/mshumer/gpt-llm-trainer). 

I have edited the prompt in order to create a dataset to fine-tune an llm like Llama 2 to return arguments to a described function in the prompt in a json readable format, similar to [OpenAI's Function Calling](https://platform.openai.com/docs/guides/gpt/function-calling) . You can find the created dataset in the ```functioncalling_gpt_dataset.pkl``` file



You can simply read the pickle file, and use the provided notebook to fine-tune your llm of choice on the dataset.
