# TeClass

This repository contains the code and dataset of the research paper titled <b>"TeClass: A Human-Annotated Relevance-based Headline Classification and Generation Dataset for Telugu"</b>, accepted at LREC-COLING 2024.

# Task Introduction
**Headline Generation** is the task of generating a relevant headline that represents the core information present in the news article. The key challenge is that, the presence of irrelevant headlines in news articles scraped from the web often results in sub-optimal performance.

As a solution to overcome this challenge, We propose that **Relevance-based Headline Classification** can greatly aid the task of generating relevant headlines.

**Relevance-based Headline Classification​** is the task of categorizing a news headline based on its relevance to the corresponding news article​ into one of the three primary classes:
  1. Highly Relevant (HREL) : The headline is highly related to the article
  2. Moderately Relevant​ (MREL) :  The headline is moderately related to the article
  3. Least Relevant (LREL) : The headline is least related to the article
    
This task has applications including _News Recommendation, Incongruent Headline Detection​​, and Headline Stance Classification​._


# Our Key Contributions

### We present "TeClass", a large, diverse, and high-quality human annotated dataset for Telugu​. 
It contains 26,178 article-headline pairs annotated for relevance-based headline classification with one of the three primary categories: ​HREL, MREL, and LREL.

### We study the impact of fine-tuning headline generation models on different types of headlines (with varying degrees of relevance to the article).
We demonstrate that the task of relevant headline generation is best served when the headline generation models are fine-tuned only highly relevant data even if the highly relevant article-headline pairs are significantly less in number.​
​
# "TeClass" Dataset Statistics
Below is the table
![TeClass_Stats_Table](https://github.com/gopichandkanumolu/TeClass/assets/54239600/4d831f89-1e80-4261-a6df-430158156af4)













Please note: Code & Dataset will be made available very soon.
