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
