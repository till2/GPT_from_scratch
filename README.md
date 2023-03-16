## 
# <div align="center">GPT from scratch</div>

<div align="center"><img src="https://github.com/till2/GPT_from_scratch/blob/main/images/Attention_is_all_you_need.jpg?raw=true" width="300" height="225"/></div>

######  <div align="center">Building & training a transformer on the first 325 episodes of the Lex Fridman Podcast to answer questions.</div>

-------------------------------

### Architecture

<div align="center"><img src="https://github.com/till2/GPT_from_scratch/blob/main/images/architecture.png?raw=true" width="830" height="900"/></div>

### Byte pair encoding (BPE)

The text is encoded with byte pair encoding (BPE) to get a vocabulary of 1,000 tokens. <br>
The number of tokens after encoding is approx. 60% of the original text length.

Here's an example of the encoding process:

```py
tokens = encode("I think this is going to be awesome.")
```

```txt
tensor([360, 237, 153,  61, 158,  61, 158, 253, 194, 186, 280,  53,  75, 169,
         67, 183,  11], device='cuda:0')
```
    
```py
len("I think this is going to take a long time.") # 42
len(tokens) # 17

decode(tokens)
```

```txt
"I think this is going to be awesome."
```


### Inference

It's not very good yet, but can mimick some english.

```py
prompt = "What do you think about language models?"
answer = prompt_model(model, prompt, max_new_tokens=800, topk=2)
print(answer)
```

```txt
>>>
I think that the sort that.
 But know?
 And there's a lot one the because the but the comple to the of the somether and of comple
 of of the because a look, the so the blange,
 but I don't some the sort of an and that the be there any had the to,
 but I'm unders to don't there there to the some of the sorther.
 And that the some that the bractive,
 but that.
 But the because actory the be the because this to that start of the some the call the of the
 and there's they're going the be exconce,
 the same that the some to through an that and of it
 of they're good, when the ARLOL the good the bedher a conver of of a conver the be of the see
 of they're good on That think to, I don't going of,
 the can the say, they like,
 they they world, you can toper one of the becople
 freed that the sorld?
 Yeah, they
```

### Notes

You can find my notes on the implementation details here: [🤖 Transformer blogpost](https://till2.github.io/blog/2023/02/17/transformers). <br>
The implementation is based on the ["Attention Is All You Need"](https://arxiv.org/pdf/1706.03762.pdf) paper and the ["Let's build GPT"](https://youtu.be/kCc8FmEb1nY) tutorial by Andrej Karpathy.


### Lex Fridman Podcast Dataset

The transcribed subtitles for the first 325 episodes of the Lex Fridman Podcast are from Andrej Karpathy's [Lexicap project](https://karpathy.ai/lexicap/index.html), which used [OpenAI's whisper model](https://github.com/openai/whisper) to transcribe them. I cleaned the data with some regular expressions to get one big corpus of text for training the transformer model.

### Training

The model was trained for ~5 hours on a GPU.

<div align="center"><img src="https://github.com/till2/GPT_from_scratch/blob/main/images/training_plot.png?raw=true"/></div>


### References

Vaswani et. al: Attention Is All You Need - [Link](https://arxiv.org/pdf/1706.03762.pdf) <br>
Andrej Karpathy: Let's build GPT: from scratch, in code, spelled out - [Link](https://youtu.be/kCc8FmEb1nY) <br>
Rasa: Rasa Algorithm Whiteboard - Transformers & Attention 1: Self Attention [Link](https://youtu.be/yGTUuEx3GkA) <br>
Thumbnail: [Link](https://makeameme.org/meme/attention-please-d7217f13d3) <br>
AI Coffee Break with Letitia: Positional embeddings in transformers EXPLAINED - Demystifying positional encodings. [Link](https://youtu.be/1biZfFLPRSY) <br>

