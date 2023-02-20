## 
# <div align="center">GPT from scratch</div>
######  <div align="center">Building and training a Transformer on the first 325 episodes of the Lex Fridman Podcast to answer questions.</div>

###### <div align="center">![attention-please-d7217f13d3](https://user-images.githubusercontent.com/89709351/220173510-65ff6b08-55fc-41b2-8c4b-9b3429f638ef.jpg)</div>

-------------------------------

### Notes

You can find my notes on the implementation details here: [🤖 Transformer blogpost](https://till2.github.io/blog/2023/02/17/transformers). <br>
The implementation is based on the ["Attention Is All You Need"](https://arxiv.org/pdf/1706.03762.pdf) paper and the ["Let's build GPT"](https://youtu.be/kCc8FmEb1nY) tutorial by Andrej Karpathy.


### Data

The transcribed subtitles for the first 325 episodes of the Lex Fridman Podcast are from Andrej Karpathy's [Lexicap project](https://karpathy.ai/lexicap/index.html), which used [OpenAI's whisper model](https://github.com/openai/whisper) to transcribe them.
Let's look at one sample episode, ep.299 with Demis Hassabis.
The subtitles are stored in the video text track (vtt) format and look like this:


### References

Vaswani et. al: Attention Is All You Need - [Link](https://arxiv.org/pdf/1706.03762.pdf) <br>
Andrej Karpathy: Let's build GPT: from scratch, in code, spelled out - [Link](https://youtu.be/kCc8FmEb1nY) <br>
Rasa: Rasa Algorithm Whiteboard - Transformers & Attention 1: Self Attention [Link](https://youtu.be/yGTUuEx3GkA) <br>
Thumbnail: [Link](https://makeameme.org/meme/attention-please-d7217f13d3) <br>
AI Coffee Break with Letitia: Positional embeddings in transformers EXPLAINED - Demystifying positional encodings. [Link](https://youtu.be/1biZfFLPRSY) <br>
