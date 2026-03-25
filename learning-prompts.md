# AI-augmented, inverted-pedagogy, Learning Prompts and Walkthrough

Here are some prompts and a walkthrough to help you run an AI-augmented, inverted-pedagogy-style learning session on any topic of your choice. The prompts are designed to guide you through the process of building a knowledge base, self-assessing your current understanding, and engaging in a Socratic learning experience with an LLM as your teacher.

**Time expectation:**
- Building the knowledge base: between 0 and 2 hours. Instantaneous if you already have the content your want to study. Long if you need to search and download a lot of content.
- Main takeaways and surprises: 10 minutes
- Self-assessment: 1 hour
- Socratic learning: 1 to 2 hours.
- **Total:** between 15 minutes to 5 hours, depending on how much content you have and how deep you want to go.

## Starting point

### Rough learning goal

Come up with a rough idea of what you want to learn and why. This is your learning goal.

### About you

Come up with a rough description about yourself. Just enough context to help the AI design a better learning experience for you.

### First prompt

```md
I want you to help me study the topic of "<your rough learning goal>". Here is a bit of context about me: <description about you>.

Keep these in mind and wait for further instructions.
```

## Build your knowledge base

You will do this differently depending if you have a clear idea of the content you want to study or not.

### Option: If you want to find content to study

Prompt:

```md
Take a moment to search for material that is relevant to study my learning goal. Look for recent developer ReXp blog pages, videos, research papers, and books. Avoid company marketing content. Give me a list of around 10 items: title, mini-summary, link
```

Review the content and if you need to correct:

```md
Now do the same kind of search, but don't limit yourself to <a, b, c...> and related practice. Use the same constraints as the previous search, but with a more general theme: <refined topic>
```

If the list is getting long and you are having troubles keeping up with it:

```md
Classify all these references by type: full content web page, full content research paper, video, book.
```

Make sure everything is accessible:

```md
Go through each item, and verify that you can access the content. Report what is missing below, so that I can get it for you  (video transcripts, research papers, podcasts transcripts, books, etc)
```

If you need, do the downloads and uploads manually, or drop the reference if you can't access it (or if it was hallucinated).

💡 **Useful tools to get content:**
- [TubeTranscript](https://tubetranscript.org/) to download transcripts of youtube videos. There are other similar tools too. And Gemini has direct access to youtube transcripts too.
- [repomix](https://repomix.com/) to download a github repo in an LLM-friendly single file
- [webmix](https://github.com/philou/webmix) a small tool I built to pack a web site in an LLM-friendly single file
- [Kindle-AI-Export](https://github.com/transitive-bullshit/kindle-ai-export) an OCR tool to generate pdfs out of kindle books

It might be a good idea to check the context size:

```md
How does all this knowledge base fit in your context window?
```

If not, you have different strategies:
- prioritize and drop some items
- split the learning by sub-topics

### Option: If you have content you absolutely want to study

For example, you might have some books in mind, or some bookmarks. You will need a DRM-free pdf version of them.

First check the context window:

```md
I plan to add <a, b, c> to the knowledge base. Do you think you will it will still fit in your context window?
```

Same as above, maybe split the learning by sub-topics or prioritize and drop some items.

Then upload the content:

```md
Add these to the knowledge base:

- url
- book
- ...

And integrate it with the rest of the content.
```

### 💡 Prefer many sources

My personal experience is that the learning is of better quality when you have a good variety of sources and don't stick to one book for example.

### Knowledge base is ready.

Notify the LLM that the knowledge base is ready.

```md
The knowledge base is ready, wait for further instructions.
```

### Refine your learning goal

Maybe you already have a better idea of your learning goal. Maybe there are sub-goals that you want to dig into more specifically. So take a minute to write all this down.

## Option: Start exploring

If you want to get 80% of the knowledge in 20% of the time, use this prompt:

```md
Before we start, go through all the content. Then, from all this knowledge base (online content + uploaded material) give me the top 5 insights and top 5 surprises related to my learning goal: <refined learning goal>
```

💡 It's a good moment to start taking notes.

💡 Again, it might be useful to refine your learning goal based on the insights and surprises you discovered.

## Self-assessment

```md
Here is how we will proceed.

I want to explore <refined learning goal>.

My main objectives for this learning exploration are:
- <insert your sub-goals here>
- ...

I want to learn by using inverted pedagogy, with the style of "Training from the back of the room", where you would act as my socratic teacher. During the process, I will take notes in my note taking system. <If you plan any other learning activity later, say so. ex: I plan to read the book xxx anyway>

You will base your teaching on all the content we gathered: online + the material I uploaded.

Your first task of my socratic teaching will be to run me through an assessment of my knowledge
- keep in mind that I did not yet study this content
- you will evaluate my answers using the perfection game
- you will ask questions one at a time
- think enough to find 10 very good questions, that cross-cut different topics, and are able to evaluate my knowledge on different topics at the same time
- the questions must remain simple and should be answerable in 4 to 5 lines max
- you will later use my assessed knowledge to build the rest of the socratic learning teaching
- Once the 10 questions are answered with feedback, wait for my next instructions

Start with the first question
```

Let yourself be guided. If you notice that it is stepping out of its socratic teacher role, remind it that it should not. Take notes as you go.

After the tenth question:

```md
Give me a summary of my current knowledge, with strengths, gaps, and opportunities for growth.
```

Review the summary and fine tune your detailed learning goals.

## Socratic learning

Let's start the socratic learning. With your gaps and opportunities in mind, you should have detailed learning priorities.

```md
First here are my priorities for learning in decreasing order
1. <insert yours>

I am less interested in the following, I might look at them later, but if ever there is something important for the rest here, don't hesitate to highlight it
- <insert yours>

Here is my overall objective <final learning goal>

To create my socratic learning path, I would like you to use the 4Cs model from "Training from the back of the room" so that you can be my socratic teacher, guiding me through the discovery of these practices and this theory.

Can you build a single learning path to study my top <n> topics of interest?

This learning path should have this format
Session 1: ...
- 4C connection
- Concept
- Concrete Practice
- Conclusion
Session2: ...
- 4C connection 
- Concept 
- Concrete Practice 
- Conclusion

and so on. You can have as many sessions as you see necessary. Each session should take between 10 to 20 minutes to complete
```

Check the learning path, and optionally ask for any adaptation you want:

```md
Start with Session 1, connection:
 
Remember I want you to be my interactive Socratic Teacher. When I say start with session 1. I mean start with the connection step. Ask me the question or activity in session1-connection, and wait for my answer. Give me feedback (perfection game again) and move on to Concepts...
```

Let yourself be guided by the Socratic Teacher. Takes notes as you go.

### Continue learning

When you reach the end of the learning plan, many options open:

- Extend the learning plan with more sessions
- Do deliberate practice on the topics you find more difficult
- Simply chat with the Socratic Teacher about the topic, to deepen your understanding and make new connections

## ⚠️ Caveats:

- If you see the Socratic Teacher is going too fast, or jumping many steps ahead, or going off-rails: tell it to get back to the learning plan.

- The Socratic Teacher might ask you "What would you do|say|code in...". Don't answer directly, the LLM can get confuse and take your words as a prompt. Instead add some context to your answer, for example:

```md
Here is what I would say:

> ...
```

## Option: Flashcards

Whenever you are finish a step, you can ask it to create flashcards for you. Here is an example prompt for Anki:

```md
I use Anki, and I want you to generate a CSV with questions of what I learned up to now.
```

And later:

```md
Generate me an Anki CSV with questions for everything I learned since the last Anki generation.
```

💡 Personal preference: Our brain space is limited, so I keep flashcards for things I need to remember "on the spot". I use a good index in my notes for the rest.

## Note taking 101

I use Cornell's note taking system with mind maps:

1. I draw mind maps as I go through the learning
2. At the end, I highlight the most important insights in the mind map
3. I write a summary of the learning in a few bullet points

💡 LLMs are becoming very good to extract the key learnings from a mind-map picture! But I still prefer to summarize myself for knowledge consolidation.