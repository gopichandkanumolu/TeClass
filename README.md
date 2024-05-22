# TeClass

This repository contains the code and dataset of the research paper titled [**TeClass: A Human-Annotated Relevance-based Headline Classification and Generation Dataset for Telugu**](https://aclanthology.org/2024.lrec-main.1364/), published at LREC-COLING 2024.
# Task Introduction
**Headline Generation** is the task of generating a relevant headline that represents the core information present in the news article. The key challenge is that, the presence of irrelevant headlines in news articles scraped from the web often results in sub-optimal performance.

As a solution to overcome this challenge, We propose that **Relevance-based Headline Classification** can greatly aid the task of generating relevant headlines.

**Relevance-based Headline Classification​** is the task of categorizing a news headline based on its relevance to the corresponding news article​ into one of the three primary classes:
  1. Highly Relevant (HREL) : The headline is highly related to the article
  2. Moderately Relevant​ (MREL) :  The headline is moderately related to the article
  3. Least Relevant (LREL) : The headline is least related to the article
    
This task has applications including _News Recommendation, Incongruent Headline Detection​​, and Headline Stance Classification​._


# Our Key Contributions

#### We present "TeClass", a large, diverse, and high-quality human annotated dataset for Telugu​. 
It contains 26,178 article-headline pairs annotated for relevance-based headline classification with one of the three primary categories: ​HREL, MREL, and LREL.

#### We study the impact of fine-tuning headline generation models on different types of headlines (with varying degrees of relevance to the article).
We demonstrate that the task of relevant headline generation is best served when the headline generation models are fine-tuned only highly relevant data even if the highly relevant article-headline pairs are significantly less in number.​
​
# "TeClass" Dataset Statistics
[comment]: # (<p align="center"> <img src="https://github.com/gopichandkanumolu/TeClass/assets/54239600/993b42c5-aa32-4cdc-b204-9fff95d7b8ec" width="400" alt="stance_category_bar_plot"> </p>)

<p align="center">
  <img src="https://github.com/gopichandkanumolu/TeClass/assets/54239600/4d831f89-1e80-4261-a6df-430158156af4" width="800" alt="TeClass_Stats_Table">
</p>


# Headline Classification Model Results
### Feature-based Machine Learning Models
<table style="width: 50%; height: 50%;">
  <tr><th rowspan="2">Feature Vector</th><th rowspan="2">Classifier</th><th colspan="5">F1-Score</th></tr>
  <tr><th>HREL</th><th>MREL</th><th>LREL</th><th>Overall <br> (Weighted)</th><th>Overall <br> (Macro)</th></tr>
  <tr><td rowspan="4">Without Feature Vector</td><td>LR</td><td>0.57</td><td>0.50</td><td>0.59</td><td>0.55</td><td>0.55</td></tr>
  <tr><td>SVM</td><td>0.55</td><td>0.49</td><td>0.57</td><td>0.53</td><td>0.54</td></tr>
  <tr><td>MLP</td><td>0.55</td><td>0.49</td><td>0.58</td><td>0.54</td><td>0.54</td></tr>
  <tr><td>Bagging</td><td>0.55</td><td>0.47</td><td>0.57</td><td>0.52</td><td>0.53</td></tr>
  <tr><td rowspan="4">Cosine Similarity</td><td>LR</td><td>0.58</td><td>0.50</td><td>0.59</td><td>0.55</td><td>0.56</td></tr>
  <tr><td>SVM</td><td>0.56</td><td>0.49</td><td>0.58</td><td>0.54</td><td>0.54</td></tr>
  <tr><td>MLP</td><td>0.56</td><td>0.49</td><td>0.56</td><td>0.53</td><td>0.54</td></tr>
  <tr><td>Bagging</td><td>0.56</td><td>0.47</td><td>0.58</td><td>0.53</td><td>0.54</td></tr>
  <tr><td rowspan="4">[Cosine Similarity, LEAD-1, Novel 1-gram %]</td><td>LR</td><td>0.61</td><td>0.53</td><td>0.59</td><td><b>0.58</b></td><td><b>0.58</b></td></tr>
  <tr><td>SVM</td><td>0.60</td><td>0.52</td><td>0.58</td><td>0.57</td><td>0.57</td></tr>
  <tr><td>MLP</td><td>0.60</td><td>0.54</td><td>0.55</td><td>0.56</td><td>0.56</td></tr>
  <tr><td>Bagging</td><td>0.60</td><td>0.51</td><td>0.59</td><td>0.56</td><td>0.57</td></tr>
  <tr><td rowspan="4">[Cosine Similarity, LEAD-1, Novel 1-gram %, Novel 2-gram %, EXT-ORACLE]</td><td>LR</td><td>0.62</td><td>0.53</td><td>0.59</td><td><b>0.58</b></td><td><b>0.58</b></td></tr>
  <tr><td>SVM</td><td>0.60</td><td>0.52</td><td>0.58</td><td>0.57</td><td>0.57</td></tr>
  <tr><td>MLP</td><td>0.60</td><td>0.50</td><td>0.61</td><td>0.56</td><td>0.57</td></tr>
  <tr><td>Bagging</td><td>0.60</td><td>0.51</td><td>0.58</td><td>0.56</td><td>0.56</td></tr>
</table>


### Fine-tuning Pre-trained BERT-based Models

#### Three Class Classification
<table>
  <tr><th rowspan="2">Pre-trained Model</th><th colspan="5">F1 Score</th></tr>
  <tr><th>HREL</th><th>MREL</th><th>LREL</th><th>Overall <br> (Weighted)</th><th>Overall <br> (Macro)</th></tr>
  <tr><td>IndicBERT</td><td>0.66</td><td>0.55</td><td>0.67</td><td>0.62</td><td>0.63</td></tr>
  <tr><td>mBERT</td><td>0.66</td><td>0.5</td><td>0.62</td><td>0.59</td><td>0.59</td></tr>
  <tr><td>mDeBERTa</td><td>0.65</td><td>0.59</td><td>0.67</td><td><b>0.63</b></td><td><b>0.64</b></td></tr>
  <tr><td>MuRIL</td><td>0.66</td><td>0.55</td><td>0.62</td><td>0.61</td><td>0.61</td></tr>
  <tr><td>XLMRoBERTa</td><td>0.67</td><td>0.53</td><td>0.65</td><td>0.61</td><td>0.62</td></tr>
</table>

#### Two Class Classfication
<table>
  <tr><th rowspan="2">Pre-trained model</th><th colspan="4">F1-Score</th></tr>
  <tr><th>Relevant<br>(FME+STC+FSE)</th><th>Less Relevant<br>(WKC+MLC+SEN+CBT)</th><th>Overall<br>(Weighted)</th><th>Overall<br>(Macro)</th></tr>
  <tr><td>IndicBERT</td><td>0.86</td><td>0.66</td><td>0.79</td><td>0.76</td></tr>
  <tr><td>mBERT</td><td>0.86</td><td>0.63</td><td>0.78</td><td>0.74</td></tr>
  <tr><td>mDeBERTa</td><td>0.85</td><td>0.69</td><td><b>0.80</b></td><td><b>0.77</b></td></tr>
  <tr><td>MuRIL</td><td>0.73</td><td>0.63</td><td>0.70</td><td>0.68</td></tr>
  <tr><td>XLMRoBERTa</td><td>0.86</td><td>0.68</td><td><b>0.80</b></td><td><b>0.77</b></td></tr>
</table>


# Relevance-based Headline Generation Model Results






Please note: Code & Dataset will be made available very soon.
