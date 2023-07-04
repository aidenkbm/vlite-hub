# vlite

a blazing fast, lightweight, and simple vector database written in less than 200 lines of code.



## usage

```python
from vlite import VLite

db = VLite()

db.memorize(["hello world"]*5)

db.remember("adele")

```

## installation

```bash
pip install vlite
```

## about

VLite is a vector database built for agents, ChatGPT Plugins, and other AI apps that need a fast and simple database to store vectors. 

I built it to support the millions of embeddings I generate , index, and sort with ChatWith+ ChatGPT Plugins which run for millions of users. Most vector databases either repeatedly crashed on a daily basis or was too expensive for the throughput I was putting through.

It uses Apple's Metal Performance Shaders via Pytorch to accelerate vector loading and uses CPU threading to accelerate vector queries to reduce time spent copying vectors from the GPU(MPS) to the CPU.

### easter egg

taken from OpenAI's tiktoken repo, I added a visualize_tokens() function to visualize BPE tokens, i made visualize_tokens to handle the output of the tokenizer.encode() function since the currently supported embeddings are based on BERT and don't use the same tokenization as GPT-4.
