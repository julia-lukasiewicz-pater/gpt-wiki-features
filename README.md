# Exploring and Analyzing Linguistic Differences between Human-generated and AI-generated Texts

Welcome to the repository for my data analysis on differences between human-generated and ChatGPT-generated texts! In this project, I dive deep into the topic to explore, analyze, and derive insights using various linguistic complexity measures. I leverage a rich dataset specifically curated for this project.

## Repository Structure

- `Code/`: Includes the Colab notebooks showcasing the process of deriving the datasets and data analysis process
- `Data/`: Contains output files from the data analysis

Check out the notebooks!

| Link | Description |
|------|-------------|
| <a href="https://colab.research.google.com/github/julia-lukasiewicz-pater/gpt-wiki-features/blob/main/Code/Creating_features_dataset.ipynb" target="_blank" style="border:none; background:none; padding:0;"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a> | Creating the dataset |
| <a href="https://colab.research.google.com/github/julia-lukasiewicz-pater/gpt-wiki-features/blob/main/Code/GPT_wiki_features.ipynb" target="_blank" style="border:none; background:none; padding:0;"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a> | Analysis |

## GPT-wiki-intro-features datasets

As part of this project, two datasets were created:
- [julia-lukasiewicz-pater/small-GPT-wiki-intro-features](https://huggingface.co/datasets/julia-lukasiewicz-pater/small-GPT-wiki-intro-features) 
- [julia-lukasiewicz-pater/GPT-wiki-intro-features](https://huggingface.co/datasets/julia-lukasiewicz-pater/GPT-wiki-intro-features)

 Those datasets are based on [aadityaubhat/GPT-wiki-intro](https://huggingface.co/datasets/aadityaubhat/GPT-wiki-intro).
 The full version contains 300k texts (150k from Wikipedia and 150k generated by ChatGPT).
 The smaller version contains 100k randomly selected texts (50k from Wikipedia and 50k generated by ChatGPT).
 For each text, various complexity measures were calculated, including e.g. readibility, lexical richness etc.
 It can be used for text classification or analysis of linguistic features of human-generated and ChatGPT-generated texts.
 


## Datasets structure

Features were calculated using various Python libraries, i.e. NLTK, [readability-metrics](https://pypi.org/project/py-readability-metrics/), [lexical-diversity](https://pypi.org/project/lexical-diversity/),
and [TextDescriptives](https://hlasse.github.io/TextDescriptives/). The list of all features and their corresponding sources can be found below:

| Column | Description | Source |
| ------ | ----------- | ------ |
| text | human- or ChatGPT-generated text | aadityaubhat/GPT-wiki-intro |
| normalized_bigram_entropy | bigram entropy normalized with estimated maximum entropy | nltk | 
| mean_word_length | mean word length | nltk |
| mean_sent_length | mean sentence length | nltk |
| fog | Gunning-Fog | readability-metrics |
| ari | Automated Readability Index | readability-metrics |
| dale_chall | Dale Chall Readability | readability-metrics |
| hdd | Hypergeometric Distribution | lexical-diversity |
| mtld | Measure of lexical textual diversity | lexical-diversity |
| mattr | Moving average type-token ratio | lexical-diversity |
| number_of_ADJ | proportion of adjectives | nltk |
| number_of_ADP | proportion of adpositions | nltk |
| number_of_ADV | proportion of adverbs | nltk |
| number_of_CONJ | proportion of conjunctions | nltk |
| number_of_DET | proportion of determiners | nltk |
| number_of_NOUN | proportion of nouns | nltk |
| number_of_NUM | proportion of numerals | nltk |
| number_of_PRT | proportion of particles | nltk |
| number_of_PRON | proportion of pronuns | nltk |
| number_of_VERB | proportion of verbs | nltk |
| number_of_DOT | proportion of punctuation marks | nltk |
| number_of_X | proportion of POS tag 'Other' | nltk |
| class | binary class, 0 stands for Wikipedia, 1 stands for ChatGPT | - |
| spacy_perplexity | text perplexity | TextDescriptives |
| entropy | text entropy | TextDescriptives |
| automated_readability_index | Automated Readability Index | TextDescriptives |
| per_word_spacy_perplexity | text perplexity per word | TextDescriptives |
| dependency_distance_mean | mean distance from each token to their dependent | TextDescriptives |
| dependency_distance_std | standard deviation of distance from each token to their dependent | TextDescriptives |
| first_order_coherence | cosine similarity between consecutive sentences | TextDescriptives |
| second_order_coherence | cosine similarity between sentences that are two sentences apart | TextDescriptives |
| smog | SMOG | TextDescriptives |
| prop_adjacent_dependency_relation_mean | mean proportion adjacent dependency relations | TextDescriptives |
| prop_adjacent_dependency_relation_std | standard deviation of proportion adjacent dependency relations | TextDescriptives |
| syllables_per_token_mean | mean of syllables per token | TextDescriptives |
| syllables_per_token_median | median of syllables per token | TextDescriptives |
| token_length_std | standard deviation of token length | TextDescriptives |
| token_length_median | median of token length | TextDescriptives |
| sentence_length_median | median of sentence length | TextDescriptives |
| syllables_per_token_std | standard deviation of syllables per token | TextDescriptives |
| proportion_unique_tokens | proportion of unique tokens | TextDescriptives |
| top_ngram_chr_fraction_3 | fraction of characters in a document which are contained within the top n-grams. For a specified n-gram range | TextDescriptives |
| top_ngram_chr_fraction_2 | fraction of characters in a document which are contained within the top n-grams. For a specified n-gram range | TextDescriptives |
| top_ngram_chr_fraction_4 | fraction of characters in a document which are contained within the top n-grams. For a specified n-gram range | TextDescriptives |
| proportion_bullet_points | fraction of characters in a document which are contained within the top n-grams. For a specified n-gram range | TextDescriptives |
| flesch_reading_ease | Flesch Reading ease | TextDescriptives |
| flesch_kincaid_grade | Flesch Kincaid grade | TextDescriptives |
| gunning_fog | Gunning-Fog | TextDescriptives |
| coleman_liau_index | Coleman-Liau Index | TextDescriptives |
| oov_ratio| out-of-vocabulary ratio | TextDescriptives |
