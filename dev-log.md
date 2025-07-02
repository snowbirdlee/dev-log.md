# Ava Lee

# 7/2/2025

> This is how inference tokens work

![Inference token](https://imgur.com/a/bhx97Lf)
---
## #What_I_Learned: INTRO TO LLM'S; creating the Base Model

> LLM stands for language learning model 🤔
### Common Crawl 📈
- 27 billion webpages
	- The internet has virtually all human knowledge
- #crawls done every 2 months
	- Crawling the internet all the time
- each crawl results in *petabytes* (1000 terabytes) of raw web data (HTML, metadata, text content, etc.)
- openly available to researchers, developers, data scientists
- powers large-scale natural language processing, machine learning, web research projects
 *this is how models get their info*
### URL Filtering ❌
Doesn't crawl...
1. abusive Sites
2. chat
3. malware
4. spamware
5. marketing
etc.
### Filtered Sites 
1. personally identifiable info
2. addresses
3. social security numbers
4. phone numbers
etc.
### Final Dataset
- 44TB of info
- 15 trillion tokens  🤯
### Project Gutenberg - Labyrinth  📖
- After 70 years, any copyrighted book **falls out of copyright** and can be available on the internet for free
- Base Models may easily access it and tell us all about it
	1. convert to binary 😱
	2. convert to bytes. 8 bits = 1 byte.
	3. ...emojis??? 🌽🤯❤️

#lossless-compression: compression w/o losing info
#lossy-compression: compress by removing some data
	- Byte Pair Encoding --> 256. *pairs repeat, so make new symbols
	- New Symbol --> 257
	- etc.

### Tokenization 💝
- a #token is a symbol that represents (words). it's a single unit of data.
- keeps making tokens until...
- max tokens: 100,277
- LLM's are comprised of tokens rather than English words

### Neural Network Training 💪
- take windows of tokens, range from 0 - 8,000 tokens. could be 4,000 or 16,000. somewhat arbitrary. Input Corpus: This ebook is for you. 
- all tokens map to a string of spaces/characters...
- words are *not* a one to one mapping to a token
- we want the base model... to ✨*predict*🔮✨ the next word by computing the probability using the 100,277 probabilities of the next token.
- there are #parameter-weights (usually billions 😱) that make this possible. 
	- these keep getting adjusted so maybe next time it's better
	- keeps adjusting until it gets it right ✅
- there's an *algorithm* (giant mathematical expression ♾️) that makes the probabilities better every time the model gets it wrong.
### Inference
- generate new tokens from the model (not in original training set necessarily)
- #inference-tokens: infer the next word (using tokens). exercising the model by running it.
- all ChatGPT is doing today is *inference*
- use *parameters and weights* to improve what comes out next
- inference is a big "token tumbler 🎲." what it picks next is based on the parameters and weights. it's sent through a tumbler and gives a token.
	- like a dice, but some sides are more probable to come up
	- it's a #stochastic (randomly determined) process. it not necessarily get the same answer each time.
- to run a good inference, you need a good GPU (hardware).

CPU is the brain of the computer

⭐️ base models aren't in chat form yet. it doesn't really answer questions. words are fed in and the model *infers* what comes next. ⭐️
- What we're feeding in is called the #context-window 🪟. It's all of the tokens you give to the LLM to *predict* the next token.
- When you give a limited number of tokens... they take *recent stuff* to fill the output.
- Models are only phrase, prediction, a bunch of tokens.
- eventually... the system memorizes *verbatim* 🗣️. 
	- but if you put something in that happens after the model is develop... it'll start hallucinating 😵‍💫
- models can realize *patterns* and continue it..... but it **WAS NOT trained‼️ WE DON'T KNOW HOW 💀**

### In Context Learning 📋📖📝
- AI models work really well even though we don't fully know how -- we only **adjust weights by giving examples**, not telling them what to do
- They sometimes **learn things we didn't expect** -- math, follow examples w/o being taught
- This is **different from normal engineering** -- normal engineering, we build step-by-step w/full understanding. NOT TRUE for AI. ❌
- AI learns **patterns from data** -- NOT rules, unlike a person's thoughts or calculator's logic 
- We can look inside the model -- still **hard to explain *why***. black box...◼️

Models get this wrong: what's greater, 9.11 or 9.2?
- ... they look at Bible verses.
- looks up this key word and the most recurrent is in the Bible.

### The Psychology of a Base Model
- token-level internet doc simulator
- stochastic; probability
- "dreams" internet documents
- recite docs verbatim from memory; "regurgitation" (ex. Wikipedia)
- parameters are lossy "zip" file of the entire internet; loses info



> *the emojis were for personal visual purposes*
> *my tags were for vocabulary purposes*


---

##  #Lab_Reflection

> The stretch of the simple-calculator lab challenged me. I constantly asked ChatGPT on how to go about the code, especially for how to calculate an expression when the user inputs it in one line. I didn't know how to get rid of whitespace if the user inputs some, which is something I need to work on for next time. The eval() function was new to me and so was .split().

---
## #Code_Snippit

> I was seeing if I could shorten my code for the simple-calculator lab. After looking at classmates' code and what we talked about in class, I included eval() and .strip() functions in my code instead of while loops I used to do:
<pre> 
num1 = input("Enter the first number: ")
operation = input("Enter the operation. Choose +, -, *, or /: ")
num2 = input("Enter the second number: ")

equation = num1 + ' ' + operation + ' ' + num2
print(f"{equation.strip()} = {eval(equation.strip()): .2f}.")
</pre>
---
## #Helpful_Links

[ChatGPT's deep research into Alan Turing's Buried Silver](https://lms.turingguild.com/courses/8/library/reck3MvZ3oUqV9eDh)

[ChatGPT](https://chatgpt.com/c/686587f2-16ec-8013-a768-32fa9a146109)

[TikTokenizer](https://tiktokenizer.vercel.app/?model=cl100k_base)


