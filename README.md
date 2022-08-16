# the_witcher_network

The Witcher character graph network, based on [thu-vu92](https://github.com/thu-vu92)/ [Thu Vu Data Analytics](https://www.youtube.com/c/Thuvu5) Youtube Tutorial.

## 1. Objective of the Project

* Creating and analysing a graphical network of character relationships of the The Witcher Book Series.
* Learning the basics of Webscraping with Selenium.
* Learning the basics of Natural Language Processing (NLP) with spaCy for Relationship Extraction.
* Learning the basics of graphs and networks using NetworkX.


## 2. Results

### 2.1 The Witcher Character Graph Network

Using [pyvis](https://pyvis.readthedocs.io/en/latest/tutorial.html) library it is possible to generate visual network graphs with minimal python code. The following graph shows a Character Graph Network between all characters of 8 books from The Witcher book series.

Visually it could be concluded the Geralt, Yennefer, Ciri and Essi are the characters with most connections (or interactions) throughout the story.

![image](https://user-images.githubusercontent.com/48052532/184943398-dfc3c0a1-5a44-466b-bca9-6e4482b6c188.png)


### 2.2 Network Analysis: Centrality Measures

Using [centrality measures](https://www.youtube.com/watch?v=NgUj8DEH5Tc), we analyse The Witcher character graph, which allows to estimate how influential or significant a character is in the story from different perspectives, as the following:

<img src="https://user-images.githubusercontent.com/48052532/184963104-6bea8b74-0bcd-475e-9e5c-3c839099074a.png" alt="drawing" width="700"/>

#### 2.2.a Degree Centrality

**Degree centrality** measures the number of nodes a node is connected to versus the total it could possibly be connected to.

We can observe that Geralt is the character that is connected (has interactions) with the most number of other characters in The Witcher books, with a centrality degree of 0.59, followed by Yennefer and Ciri with 0,26 and 0,19 centrality degrees respectively.

<img src="https://user-images.githubusercontent.com/48052532/184936596-6d7761ef-6e96-4094-aa31-e95eefa756e5.png" alt="drawing" width="350"/>

#### 2.2.b Closeness Centrality

**Closeness centrality** tries to capture how close a node is to any other node in the network. 

We can observe that Geralt has the highest closeness measure of 0.66, followed again by Yennefer and Ciri with a 0.47 and 0.46 closeness measure respectively. This can be interpreted that the mentioned characters can more easily or quickly reach out to any other character in the story.

<img src="https://user-images.githubusercontent.com/48052532/184936894-7b749cce-7e49-4d72-856d-60c900be499d.png" alt="drawing" width="350"/>


#### 2.2.c Betweenness Centrality

**Betweenness centrality** tries to capture the nodes role as a connector or bridge between other nodes or groups.

We can observe that Geralt is the character that has the highest betweenness measure by far, with 0.68. This might mean that he has a role of liason and intermediary between other characters and also, that he controls the flow of information.


<img src="https://user-images.githubusercontent.com/48052532/184938032-479f04e7-89e4-42f9-b791-7e724e1900df.png" alt="drawing" width="350"/>

#### 2.2.d Eigenvector Centrality (Prestige Score)

**Eigenvector centrality** tries to capture how relevant a node is based on the significance of the nodes it is connected to. In other words, how connected to influential nodes a node is.

We can observe that once again Geralt is the character with the highest score, with a eigenvector measure of 0.50. It is followed by Yennefer and Boholt with 0.33 and 0.29 scores respectively. This could be interpreted that the mentioned characters are the most connected to other influential and highly connected individuals.


<img src="https://user-images.githubusercontent.com/48052532/184941671-e7d0e778-a0e7-41de-ba31-4e69a94e864f.png" alt="drawing" width="350"/>


### 2.3 Network Analysis: Community Detections

Using [community louvain package](https://python-louvain.readthedocs.io/en/latest/api.html) "it is possible to compute the partition of the graph nodes which maximises the modularity (or try..) using the Louvain heuristices".

In the graph we can observe that there are 5 communities detected. The most significant community (blue) has Geralt as the primary point. Next comes the yellow community surrounding Yennefer and the pink community, where Ciri is the central point.

<img src="https://user-images.githubusercontent.com/48052532/184916802-6bc1dd62-0190-45c4-9b6b-c837ed0d98cb.png" alt="drawing" width="800"/>

### 2.4 Evolution of Character Importance: According to Degree Centrality

In order to evaluate the relevance on characters throughout the different books of ther series, we calculate the degree centrality per character in each individual book. In the following graph, we can see how Geralt's, Yennefer's and Ciri's protagonism developes in the eight books analysed.

We can observe that until the forth book of the series Geralt is the central character, after which Ciri takes the lead and in the final book, it is Yennefer that could be considered to have the most protagonism.

<img src="https://user-images.githubusercontent.com/48052532/184954564-cc187724-82fa-427a-b311-6d04c910c572.png" alt="drawing" width="500"/>

## 3. Notebooks and files

* [witcher_character_scraping.ipynb](https://github.com/IsiAlas/the_witcher_network/blob/main/witcher_character_scraping.ipynb) : Notebook with web scraping process with a data frame of characters present in each book in .csv format as output.
* [character_networks.ipynb](https://github.com/IsiAlas/the_witcher_network/blob/main/character_networks.ipynb) : Notebook with the process of creating and analyzing The Witcher character graph network.
* [character.csv](https://github.com/IsiAlas/the_witcher_network/blob/main/character.csv) : dataframe of character present in each book in csv format.
* [functions.py](https://github.com/IsiAlas/the_witcher_network/blob/main/lib/utils/functions.py) : script with relevant functions to loop through all books and identify entities (characters) and create a relationships dataframe.
* [data folder](https://github.com/IsiAlas/the_witcher_network/tree/main/data): Contains The Witcher book series in text format

## 4. Sources

* Project Based on YT tutorial:
  - Python Web-scraping with Selenium vs Scrapy vs BeautifulSoup | Witcher project ep. #1 [Youtube Video Link](https://www.youtube.com/watch?v=RuNolAh_4bU&t=13s)
  - Network of The Witcher | Relationship Extraction & Network Analysis with Spacy & NetworkX [Youtube Video Link](https://www.youtube.com/watch?v=fAHkJ_Dhr50)

* For Webscraping process: 
  - [Witcher Fandom Wiki](https://witcher.fandom.com/wiki/Category:Characters_in_the_stories)

* The Witcher Book Series in Text File
  - [Thu Vu Project Repository](https://github.com/thu-vu92/the_witcher_network/tree/main/data)
  
* Centrality Measures:
  - [Degree Centrality](https://www.youtube.com/watch?v=iiVeQkIELyc) - John McCulloch Youtube Channel
  - [Betweenness Centrality](https://www.youtube.com/watch?v=0CCrq62TF7U) - John McCulloch Youtube Channel
  - [Network Centrality](https://www.youtube.com/watch?v=NgUj8DEH5Tc) - Systems Innovation Youtube Channel
