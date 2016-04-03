## The Reading Algorithm

As a lifelong learner and as a Software Developer I find myself constantly confronted
with the necessity to learn new things. This article then is a collection of my thoughts about the process of learning, specifically as a function applied during the reading of texts. I will attempt to define a general algorithm which I have been developing for some time now, and I will try to give some tools you can use to evaluate your own algorithms.

#### Definitions

Before we begin I would like to give some definitions so the reader may clearly understand the concepts to which I refer in the following essay.

1. **learning** : the acquiring of new knowledge which a person can apply in a given set of tasks at any proceeding point in time, such that the pure recitation of the newly understood material is not a member of the task set.

2. **intuition** : a state of mind initiated through an act on the sense(s) by some external object in which the object acting on the sense(s) is immediately understood without reflection or guided thought.

#### What is the goal?

Our goal when reading to learn, implies that we should develop our ability to apply new understanding to various sets of tasks. In addition, I feel that it is only through learning that we can develop our intuitions about things. The development of intuition is, in my opinion, the highest level of understanding obtainable. It is immediate understanding, like the language we use in every day speech, the letters on a page or sounds in the air which we intuitively understand as words and sentences.

Unless a person acquires brain damage, they will not forget language, they will not forget the fundamental arithmetic operations, or the abilities to run, and jump and climb. These are for almost all humans intuitive faculties. I'm of the opinion that, at least for the task of reading, learning should have intuition as its goal.

#### Why we need a test method

If we accept that with an algorithm we can improve the process of learning, we realize we need a way to test the effectiveness of our algorithms. If not rigorously, at least for ourselves as learners.

In a first approach, we could just read texts, attempt to absorb as much information as possible and be happy if we were to be capable of achieving the reproduction of some percentage of that which has been read, say 50% or 70% or 90%. I will call this approach the `regurgitation-test`.

There are several problems with this notion. The first is that being able to regurgitate even a high percentage of some text does not necessarily encompass the understanding of that text, which is vital for learning.  And secondly, the general problem, is that the `regurgitation-test` tells us nothing about the change in our "units of knowledge", our intuition, or our ability to apply what we have learned after our reading task has been undertaken. So with that method we can't say whether we have learned anything, and we can't test our intuition either.

Thus, although the `regurgitation-test` is a failure, it provides us with the characteristics we would like to have in a test method, which are for our purposes the following:

1. How have our knowledge units changed?
2. How has our understanding and application of the knowledge units changed?
2. How has our intuition changed?

And that is our test method. I will call it the `KAI-delta-test` which stands for the Knowledge, Application and Intuition change test. It tells us everything we want to know about learning. We can check what new knowledge units we have acquired - which is essentially the `regurgitation-test`, we can check how well we can apply the new material, and lastly does it require less mental effort to grasp the material than before we began our reading task (intuition).


#### The Algorithm

Now we have a way to test whether, and to what degree, we have learned during a reading task. So let's describe the general program of learning by reading.

```
learning-by-reading ::= <set-goals> <active-reading> <summarize>

active-reading ::= <ask-questions> | <test-assertions> | <solve-problems> | <create-problems> | <reflect> | [<active-reading>]

```

Here are the definitions.

`set-goals` means you should know exactly what you want to learn. This precedes all other operations. Perhaps, your goal is to learn how to do polynomial division or how Big-Oh notation works. Imagine a pathway in your mind leading up to the goal and as you engage in `active-reading`, ask yourself: what effect does this material have on the path towards that goal? The Goal Set should be omnipresent in the back of your consciousness during `active-reading`.

`active-reading` is an active recursive process. You cannot read for learning like you would when reading a novel. That will not work. Think that you are `doing` the material i.e. you are `doing` algorithms or `doing` economics or `doing` game theory, never reading about them.

`ask-questions` ask yourself questions about the material, feel free to question the author and his statements, don't take everything he says for true, think about why it the statements are correct or incorrect and how they lead you along the path towards your goal.

`test-assertions` test everything you can. If the text describes how to calculate using Euclid's GCD algorithm, get a sheet and paper and test it out, ideally with a bunch of different numbers and combinations.

`solve-problems`, `create-problems` if there are problems and exercises in the text, do them all. If not, look for key indicators that are guiding you along the path towards your goal and create your own exercises and problems. Look for edge cases and try to refine and clarify the path which is your reading journey towards your `set-goals`.

`reflect` think about each object as you approach it. How does it help you understand the material? Why is it essential? What would happen if it were left out?

`summarize` means to talk about, discuss, or write out in your own words the concepts conveyed by the text. You can do this after you reach the end of subsections or even paragraphs, but always do it once you think you have reached the end of your journey and arrived at your `set-goals`.

#### Summary

All learning should strive to improve intuition. We have seen an algorithm for approaching the task of learning through reading and been given a general procedure and guidelines for testing our own approaches to that process.

I hope this article is insightful and I would enjoy feedback and to see others algorithms applied to the process.
