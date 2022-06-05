---
layout: post
comments: true
title: "From Programming to Creativity: Human-AI Collaborated Generation"
author: Feiyang Chen, Wenhe Zhang
date: 2021-04-18
---


> Our survey focus on two human-AI collaborated geenration tasks: Human-AI Programming and Human-AI Co-Creation. Currently human plays the leading role in both tasks, but the level of collaboration differs in the two tasks. Future work need to strengthen AI's abilities on generation tasks as well as improve the communcations between human and AI during collboration.

<!--more-->
{: class="table-of-content"}

* TOC
{:toc}

## Introduction


In recent years, Artificial Intelligence(AI) technologies' striking performance has drawn people's attention to a new area "Human-AI Collaboration", where human and AI work together towards a shared goal. Various forms of collaborations were achieved on an array of tasks, including medical diagnosis, autonomous driving, artistic creation, programming, teaching, and decision-making. These tasks could further be categorized as prediction tasks or generation tasks. Prediction tasks usually require "human+AI" team to make correct predictions before taking actions, while generation tasks need human-AI teamwork on producing fit-for-purpose or creative contents.

In this survey, we will focus on human-AI collaborated **generation** tasks, where human and AI work jointly to create visual, audio, or text contents, such as code, stories, poems, paintings, and music. Generation tasks are challenging for both human and AI, as it involves multiple steps before completion, communications between teammates, observations on existing work, imitations of examples, and production of new contents. It is also hard to have explicit criteria of "good generations" in many situations, which leads to difficulties in improving human-AI collaborated generation. Delving into such a challenging but intriguing area, we have two initial questions: 

- To what extent is the ongoing collaboration between human and AI on generation tasks? 

- Does AI or human contribute more in human-AI generation tasks?

Our investigation was centered on two streams of generation tasks: human-AI programming and human-AI co-creation. We will introduce the current progress, as well as the limitations and future directions. We hope to extract common insights from these two streams of tasks, and shed light on the future of human-AI collaboration.

## Human-AI Programming

Computer programming is the process of performing a particular task by building an executable
computer program. Once a programmer knows what to build, the act of programming can be thought
of in 2 steps: 1). breaking a problem down into simpler problems; 2). mapping those simple problems
to existing code (libraries, APIs, or functions) that already exist1. The latter is often the least fun
part of programming (some repetitive/redundant work) and the highest barrier to entry (depends
on proficiency in a programming language). This makes people think: can AI help human do
programming such "boring" yet important tasks? The answer is affirmative. With the eye-catching
success of AI models (especially large language models) in many domains [1– 6] and the presence
of code in large datasets [7], as well as the resulting programming capabilities of language models
trained on these datasets [ 8 ], these models have also gradually been applied to program synthesis [9],
i.e. AI models collaborate with human to do programming, namely Human-AI Programming

### Current Progress



Traditional program synthesis is usually from a natural language specification through utilizing
a probabilistic context free grammar (PCFG) to generate a program’s abstract syntax tree (AST)
[ 10 –13 ]. With the resurgence of deep learning and the success of large language models [14 , 15 ],
large-scale Transformers have also been applied to program synthesis. CodeBERT [ 16 ] is based
on Transformer neural architecture and has been trained with a hybrid objective function, to learn
general-purpose representations that support downstream applications such as code search, code
documentation generation, etc. PyMT5 [17 ] is a text-to-text transfer transformer especially for
the PYTHON method, to translate between all pairs of PYTHON method feature combinations
(non-overlapping subsets of signature, docstring, body). Similar in spirit to PyMT5 [17], Codex [ 18]
is a GPT language model fine-tuned on publicly available code from GitHub, which displayed strong
performance on HumanEval dataset (including a set of 164 hand-written programming problems).
Codex [18] is most capable in Python, but it is also proficient in over a dozen languages including
JavaScript, Go, Perl, PHP, Ruby, Swift and TypeScript, and even Shell, whose descendants power
GitHub Copilot2, an AI pair programmer that helps human write code faster and with less work. More recently, AlphaCode [ 19] shows more complex programming ability, which focuses on competition-
level code generation and achieves on average a ranking of the top 54.3% in competitions on the
Codeforces platform. CODEGEN [ 20] is a conversational program synthesis approach via large
language models, which casts the process of writing a specification and program as a multi-turn
conversation between a user and a system, outperforming Codex [18 ] on the HumanEval benchmark.

### Future Efforts

Although large language models have made some progress in Human-AI Programming,
there are still a number of limitations. Take Codex [ 18 ] as an example. First, such large language
models are not sample efficient to train. Their training dataset comprises hundreds of millions of lines
of code, even seasoned programmers may not encounter anywhere near this amount of code over their
careers. But Codex still only solves easy-level problems, in that case, a junior student who completes
an introductory computer science course is even expected to be able to easily beat Codex-12B [ 18].
Second, model performance degradation as docstring length increases, which means Codex struggles
to parse through increasingly long and higher-level or system-level specifications. Third, Codex have
difficulty with binding attributes to objects, especially when the number of operations and variables
in the docstring is large. So back to our previous questions: 1). To what extent is there ongoing
collaboration between human and the AI system? Apparently, it’s only **limited collaboration** at the
moment based on the above limitations for Human-AI Programming. 2). Does the AI or human agent
contribute more to the system’s decision-making/action-taking? Currently, human still **dominate** and
contribute more to programming tasks. In the future, we expect AI models to address more complex,
unseen problems that require true problem-solving skills beyond simply translating instructions into
code so that achieving a higher degree of Human-AI Collaboration.

## Human-AI Co-Creation

Involving the active use of imagination and innovation, creativity was once considered unique to
human [21 ]. As the emergence of AI technologies, some researchers proposed a concept named "AI
creativity"[ 22 ], which refers to the ability for human and AI to co-live and co-create by playing to each
other’s strengths. In line with this concept, recent research work incorporated AI collaborators into
human’s creation process, especially the process of artistic creation. For example, AI drummers were
developed to collaborate with human musicians in musical improvisation and live performance[ 23 ];
DuetDraw provided an interface allowing users and AI agents to draw pictures collaboratively[ 24];
NLP models and human collaborated on creative writing tasks, such as short story writing[25].

### Current Progress

The goal of human-AI co-creation is not to replace human creativity or automate the creation
process[25 , 24 ]. Although closely collaborating with AI, human participants play the leading role
in creation. In contrast, AI systems are designed as complements to human creativity[22 ], which
could provide suggestions for next steps or complete some repetitive tasks in creation. For example,
in collaborative story writing, AI suggests new writing ideas as a story unfolds[ 25 ]; when drawing
pictures collaboratively, AI could automatically draw the same object that a user has just drawn in a
slightly different form[24 ]. Results of user studies align with such a human-centered design: users
prefer to take the initiative when collaborating with AI; major and creative tasks should be assigned
to human while repetitive and arduous task should be assigned to AI[24].

Compared with human working alone, incorporating AI collaborators could improve both user
performance and user experience in creation process:

- AI could *inspire* human’s creativity, especially when human get stuck in creation process.
  For example, in DuetDraw[ 24], AI models could point out an empty space on the canvas,
  where user may further add new objects.
- Human have various *positive experiences* through interaction with AI. When drawing pic-
  tures collaboratively, users are delighted to see the unexpected objects drawn by AI[ 24 ]. In
  collaborative story writing, users enjoyed writing with AI’s suggestions[ 25 ]. AI collabora-
  tors also allow users, especially less experienced writers, to write in a judgement-free setting
  without pressure from human collaborators[25].

### Future Efforts

Although promising, human-AI co-creation is a new and developing area with challenging problems
to solve. One of the outstanding problems faced by human-AI co-creation is the communication
between human and AI during creation process. In group collaboration for artistic creation, human
creators not only convey arts-related information to other creators, but also send and receive non-arts
cues, such as body language and eye contact, from which creators could identify the intentions of their collaborators. However, when it comes to collaboration with a non-human creator, these
important cues are missing in the creation process[23 ]. This could negatively influence the efficiency
of collaboration and the trust built between human and AI in co-creation.

To improve the communication between human and AI, there are some future efforts to take:

- For the communication  *from human to AI*, researchers need to take more "social cues"
  into consideration[26]. Future research work could borrow measurement methods from the
  area of psychology and cognitive science. After quantifying human participants’ emotion,
  attention, engagement, and intention, AI models could utilize these behavioral data to better
  learn about their human collaborators.
- For the communication  *from AI to human*, including explanations and confidence into the
  conveyed information will help build trust in collaboration[22]. Moreover, the suggestions
  provided by AI collaborators need to keep a balance between coherence and novelty[25 ]:
  while novel and surprising suggestions could inspire human creators, they can be distracting
  and far away from the creation goal.

Besides improving communication, there are also other future directions of human-AI co-creation.
Building general framework for human-AI collaboration in creative activities will simplify the devel-
opment of related applications and facilitate the comparison of different research work. Meanwhile, it
is also critical to thoughtfully design task-specific patterns in AI systems that accommodate different
creation tasks. With continuous improvements, we believe "AI creativity" will bring tremendous
inspirations to arts and science in the future.

## Discussion



Comparing human-AI prgramming and human-AI co-creation, we noticed some similarities between the two generation tasks. Humans are in dominant positions for both of the tasks. AI could assist people in writing code or creating artwork, but it could not replace human programmer or human artists. Human participants also hope to take the leading role instead of simply following AI's suggestions or actions.

The difference between the two generation tasks lies in the level of collaboration. For human-AI programming, there are limited collaborations between human and AI. The duty of AI is usually only translating the natural language instructions into code. In contrast, human-AI co-creation involves close collaboration between human and AI creators. AI need to give suggestions based on the current work at each step of the creation task. Although human takes the dominant part in both of the tasks, AI's roles are slightly different: For human-AI programming, AI is usually viewed as a "coding assistant" that fulfills the requirement from human programmers; For human-AI co-creation, AI is regarded as a creator that provides recommendations and inspirations for human artists. We think this is mainly because code generation is a relatively new area where current code generation methods are not as strong as image or text generation methods, so that people tend to view AI as an assistant instead of a partner during coding.

The investigations on human-AI programming and human-AI co-creation provide us with insights into the future work of human-AI generation tasks, or even the larger area "Human-AI Collaboration":

- To achieve higher level of collaboration, we need to **strengthen AI's ability** on corresponding tasks. For example, code generation methods could be improved to solve more complex coding problems and process more complicated instructions from human. Besides performance, the interpretability and generalization ability are also equally important. 
- **Communication** is the essential part of human-AI generation tasks. It is worth noticing that the communications in human-AI collaboration are bi-directional: Human convey task-related information, intentions, emotions, and expectations to AI, while AI gives suggestions, confidence score, and explanations to human. We need to take both directions into consideration when designing human-AI collaboration systems.

## Conclusion

In this survey, we delved into two human-AI collaborated generation tasks: Human-AI Programming and Human-AI Co-Creation. In both of the tasks, human plays the dominat role and AI could help human complete tasks or inspire human with new ideas. Our investigation shows that both "human factors" and "AI factors" are indispensible components in human-AI collaboration. Future work needs to work on the improvement of AI's ability as well as the bi-directional communication between human and AI  during collaboration. 

## Reference



---
