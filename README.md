# Covid-related tweets inside and outside China

![alt text](https://github.com/silviapoletti/Covid19-related-tweets-Network-Analysis/blob/29212b9b7dfdf89332fc3fcada2d82686137e2bf/Images/Network%20Science.png?raw=true)

Data has been collected from the following Twitter accounts:
- inside China: `CGTNOfficial`, `XHNews`
- outside China: `AJEnglish`, `AP`, `BBCWorld`,  `CNN`, `Reuters`

Periods of time for which data has been collected:
- from 22/01/2019 to 22/02/2019 -> early pandemic
- from 20/09/2020 to 21/10/2020 -> turning point of the epidemic and the serious controversy between Chinese and foreign media. At the UN General Assembly Trump criticized the Chinese government, and the Chinese media and the Ministry of Foreign Affairs refuted it. At the same time, China’s economy began to grow and became the only major economy in the world with positive growth.
- from 17/03/2021 to 17/04/2021 -> WHO released traceability report. CGTN and BBC reported the news about this report in different ways: CGTN said WHO said Wuhan was not the only possible Covid source, but BBC said Covid comes most likely from China. Also, during this time, China vaccine was reported not to work, but inside-China accounts may avoided to talk about that.

Keywords used to collect the data:
- first period -> `china`, `coronavirus`, `covid`, `wuhan`
- second period -> `china`, `coronavirus`, `covid`, `wuhan`, `vaccine`
- third period -> `covid`, `vaccine`, `WHO` (`delta` has been excluded)


## Exploratory Analysis

In order to try to get some insights about the collected data, we decided to perform an initial exploratory analysis.
This section is entirely dedicated to the presentation of the methods we used in order to extract information from the “China” and “outside China” tweets.
In particular, we did some exploratory analysis on the network using the main centrality measures.

The following is a log-log plot of the degree distribution of the two networks: the behaviour is almost equal in the two graphs, except for a small shift to the left of the China mean degree. It worths also noticing that for big enough degrees the two distributions follow a power law pattern.

![alt text](https://github.com/silviapoletti/Covid19-related-tweets-Network-Analysis/blob/e0c05830628538215f035f5ed3e9f0497b16bf57/Images/degree_distributions.png?raw=true)

In order to better understand the structure of the networks, we investigate its robustness capabilities. 
To do that we look at the behaviour of the number of connected components and of the size of the giant component under different nodes removal strategies, i.e. attacks:
• Random failure: we remove random nodes;
• Hubs removal: we remove the words with an higher degree first;
• Closeness removal: we remove the nodes with higher closeness centrality first;
• Betweenness removal: we remove the nodes with higher betweenness centrality first.

Inside China and Outside China networks behave in a similar way as described in the following figure.

![alt text](https://github.com/silviapoletti/Covid19-related-tweets-Network-Analysis/blob/3168c6707d1b34c549bb90b9e818faf038dde005/Images/A_T.png?raw=true)

In order to get some statistical significance from our analysis, we decided to test some probabilistic models that tries to capture the generative process behind the network itself. In particular, we tried p2-ergm and AME models.
After fitting the model on both of the networks, we compared additive effects for the highest common Pagerank nodes as shown in the following.

![alt text](https://github.com/silviapoletti/Covid19-related-tweets-Network-Analysis/blob/779ee67da35bab7c3e3d6d913b351621fc28d049/Images/additive_effects_ame.png?raw=true)

The next figure represents the “best superposition” of latent nodal representations of the highest Pagerank words in the two networks:

![alt text](https://github.com/silviapoletti/Covid19-related-tweets-Network-Analysis/blob/779ee67da35bab7c3e3d6d913b351621fc28d049/Images/latent_effects.png?raw=true)

Finally, we have a boxplot comparison of the amen-simulated PageRank marginal distribution for the highest PageRank words in the two networks:

![alt text](https://github.com/silviapoletti/Covid19-related-tweets-Network-Analysis/blob/779ee67da35bab7c3e3d6d913b351621fc28d049/Images/simulated_pr_usa.png?raw=true)


## Community Detection
We identify the hidden relationships that may exist among the nodes in a network, indicating communities of nodes. 
We implemented six different strategies to carry out the task: Kernighan–Lin bipartition, dendrograms, Clauset-Newman-Moore and Louvain method (modularity maximization) for discovering some relevant network partitions, while Big CLAM and Clique percolation for highlighting possibly overlapping communities.

The following are examples of community detection graphical representation:
![alt text](https://github.com/silviapoletti/Covid19-related-tweets-Network-Analysis/blob/29212b9b7dfdf89332fc3fcada2d82686137e2bf/Images/den-all.png?raw=true)
![alt text](https://github.com/silviapoletti/Covid19-related-tweets-Network-Analysis/blob/29212b9b7dfdf89332fc3fcada2d82686137e2bf/Images/China_louvain.png?raw=true)
