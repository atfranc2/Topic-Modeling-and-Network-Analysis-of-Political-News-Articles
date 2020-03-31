# Topic-Modeling-and-Network-Analysis-of-Political-News-Articles

## Summary
The objective of this analysis is to explore the relationships that various new organizations form with a set of topics that are discussed in political news sections relating specifically to the 2020 presidential election cycle. The purpose of performing this analysis is to propose a methodology for exploring how well different news organizations cover latent topics in political news, so that readers can choose outlets that are more representative of a broad range of topics.

The analysis is constrained to analyzing articles categorized as political news articles that populate search queries when searching for news related to the 2020 presidential election. Links to about 1500 political news articles were collected by using the Azure Bing Search API. The BeautifulSoup module in Python was then used to scrape article text from the collected links.
By using the political news data that we collected, we are interested in finding the potential relationship among the news articles and the news topics discussed across a corpus of documents. Latent Dirichlet Allocation (LDA) and Latent Semantic Indexing (LSI) were employed to model latent topics across the corpus of documents. The coherence score from LDA was used to find the optimal number of topics to use in the analysis. The coherence score suggested that 16 topics was the optimal number to use, and this number of topics was also used for LSI. 

The scores from LDA and LSI were used to construct a document-topic network showing links between the documents and the topics that they discuss. The document-topic matrix was also used to find the cosine similarity between documents according to their topic composition. The cosine similarity matrix was used to construct a document-document network.
In the document-document similarity network modularity, was used to find document communities and quantify their connectivity to other documents. The modularity of the LDA document-document similarity network was 0.376 with 7 document communities and the modularity of LSI was 0.303 with 6 document communities. Figure 1 shows the LDA document-document similarity network with nodes colored by their respective modularity classes, nodes sized by their degree, and edges colored by their cosine similarity to other documents.


![GitHub Logo](https://github.com/atfranc2/Topic-Modeling-and-Network-Analysis-of-Political-News-Articles/blob/master/LDA%20Network.png)

**Figure 1:** LDA document-document topic similarity network



## Dataset
The dataset contains 1736 documents collected from online political news articles from 475 different news organizations written between February 1st, 2020 and March 6th, 2020.  We used the Microsoft Azure Bing News Search API to collect links to political news articles. Once the article links were obtained we scraped the article text from each website using the BeautifulSoup module in Python. The search terms used to collect article links are listed below: 

**Table 1:** Terms used in the Bing search query to collect article links
Query Terms | Query Terms Continued
------------ | -------------
USA Election Politics | Democratic National Convention 2020 
2020 Presidential | Election Presidential Debates 2020 
Joe Biden | Micheal Bloomberg 
Bernie Sanders | Trump Rally
Pete Buttigieg | Democratic Caucus 2020 
Donald Trump | Politics United States
Super Tuesday | 2020 Presidential Election Opinion
Republican National Convention 2020 | 



## Methodology
Scrapes political news article links using the Microsoft Azure Bing Search API. Then BeautifulSoup  is used to scrape article text. The articles are then prepossessed using tokenization, stop word removal, and porter stemming. LDA and LSI topic modeling are used to find latent topics. The cosine similarity of topic composition is then computed for each method. Finally a force directed network visualization is constructed in Gephi. 

![GitHub Logo](https://github.com/atfranc2/Topic-Modeling-and-Network-Analysis-of-Political-News-Articles/blob/master/Topic%20Modeling%20Work%20Flow.png)

**Figure 2:** Workflow of article collection, topic modeling, and network analysis


## Results

**Table 2:** Summary topic compositions of the 10 most prevalent news organziations in the dataset
Organization | Topic Count |	Topic List
------------ | ------------- | ------------
YAHOO! |	7 |	Topic 1, Topic 4, Topic 7, Topic 8, Topic 10, Topic 14, Topic 15
MSN |	7 |	Topic 2, Topic 8, Topic 9, Topic 10, Topic 11, Topic 14, Topic 15
International Business Times |	5 |	Topic 7, Topic 8, Topic 10, Topic 11, Topic 14
Reuters |	4 |	Topic 2, Topic 8, Topic 9, Topic 11
USA Today |	3 |	Topic 7, Topic 8, Topic 14
Politico |	3 |	Topic 1, Topic 5, Topic 15
Fox News |	3 |	Topic 5, Topic 7, Topic 10
Business Insider |	3 |	Topic 7, Topic 8, Topic 15
Washington Post |	2 |	Topic 7, Topic 14
New York Times |	2 |	Topic 5, Topic 15

# References
1. Sarkar, Dipanjan. "Text Analytics with Python." (2016).
2. Bail, Christopher Andrew. "Combining natural language processing and network analysis to examine how advocacy organizations stimulate conversation on social media." Proceedings of the National Academy of Sciences 113.42 (2016): 11823-11828.
3. Microsoft Azure. Bing Search API. 
