scraping of the data: 
we used about 1000 nodes of each of the major topics like trigonometry, algebra, etc and did a BFS traversal to generate our dataset.
for each page we extract first 12 p tags and all the valid out links from that page(the ones not with %,user,identifier, etc in their links), page title and page link.

Class Vertex:  #nodes of the graph
for each node it stores label, link, neighbour_list, keyword from the text, NLP features(BOW, TFIDF), degree centrality, tags
and clustering cofficient.


Class Graph:    #stores the Graph
stores the vertices(vert_dict) and links(keys of the dictionary) as a dictionary.


Labeling of the data:
we used the labeled data and extracted their top 10 <p> for creating the feature vector for those nodes.
then we compared the dot product with each of our nodes and the most similar node gets the tag of that labeled node.
the graph neural network cannot be applied here as the graph is quite large and the labeled data is quite small dued to which many wrongly labeled nodes will  be assigned.
instead by comparing as above mentioned will give a better labeling to the nodes.

node ordering:
We tried to come up with an ordering algorithm such that for a given topic we could find the relevant pages and pass the ordering according to the labels we provide and the outlink that page carry. We design BFS, DFS and by label ordering.


