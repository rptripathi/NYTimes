# Topic recognition on New York Times articles

<img src="Assets/ErdosLogoNewSmall.png" alt="The Erdős Institute" height=40></img>&nbsp;&nbsp;<img src="Assets/poweredby_nytimes_200a.png" alt="Powered by The New York Times"></img>

Project created by Ravi Tripathi, Touseef Haider, Ping Wan, Schinella D'Souza, Alessandro Malusà, and Craig Franze for the Erdős Institute Data Science bootcamp, May-Summer 2024 Cohort, mentored by Matthew Graham. Data provided by The New York Times.

### Goals

Analyze New York Times articles by topic and explore applications such as
- Building a recommendation system based on topic similarity;
- Analyzing correlations between topics;
- Verifying accuracy of keywords and/or suggesting additional ones;
- Evaluating trends in topic frequency.

### Stakeholders

As stakeholders for this project, we envision our team members (Ravi Tripathi, Touseef Haider, Ping Wan, Schinella D'Souza, Alessandro Malusà, Craig Franze) and the New York Times, or potentially any online news platform.

### Key performance indicators

In the models we implemented, a topic is represented as a collection of words, each with a weight expressing its relevance, or the probability of it being used in an article about the given topic. KPIs for the detection of topics from the document collection are then:
- Sparsity/separation of the topics, viewed as vectors of weights;
- Recognizability of a topic from the list of most relevant words;
- Perplexity, a metric that measures how "surprised" a trained probability model is when presented with new data points.

KPIs for the assignment of topics to individual documents include:
- Ability to recognize similar topics from separate parts of the same article;
- Consistency of topics detected with titles and keywords.

Given the time constraint on this project, we focused primarily on the distribution of topics on the collection.

## Methods

We used two main methods: Latent Dirichlet Allocation (LDA) and Bidirectional Encoder Representations from Transformers (BERT).

<!-- Expand -->

## Data

The dataset we used was obtained from The New York Times via their official API. We considered all available metadata of articles published between May 15th, 2023 and Mat 14th, 2024, for a total of about 42,000 data points. We identified a few fields that seemed to lend themselves to the task and chose for simplicity to focus on one, the abstract.  
During data exploration we identified two major classes of articles with nearly identical abstracts and no discernible topics, which we discarded alongside data points with invalid abstracts. We then split each abstract into individual words (or *tokens*), including acronyms and year dates, and then disregarded all non-acronym words below three characters in length. We also analyzed the word count distribution after the cleaning process to decide whether to eliminate articles below a certain length.

![word count distribution](Assets/word_count_distribution.png)

The code we used for scraping and preprocessing the data can be found in our [preprocessing Jupyter notebook](Notebooks/preprocessing.ipynb).

## LDA approach

## BERT approach

## Future directions

Our project could be continued in a number of ways given the appropriate amount of time and resources. Possible improvements include:
- Exploring other fields available in the metadata, such as `'lead_paragraph'` and analyze the results in comparison to those obtained thus far;
- Refining our tokenization and lemmatization processes, e.g. to better detect acronyms and identify stop words more accurately;
- Adjusting the many hyperparameters available in LDA and BERT, e.g. the criteria for which words to include in the vocabulary;
- Further analyzing the performance of our model by including additional metrics to the validation;
- Developing a user interface for the recommender;
- Implementing a version of the recommender that offers multiple options and uses the history of choices made to improve its suggestions.

Additionally, our recommender could be further improved by combining it with analysis of additional data. If given access to data on article popularity, content consumption, and perhaps user demographic and preferences, this information could be combined with topic similarity to build a more robust recommendation system.
