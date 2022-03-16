# Covid-related tweets inside and outside China

![alt text](https://github.com/silviapoletti/Covid19-related-tweets-Network-Analysis/blob/ecfbd8365ca7cad2976aa6a9ef5a0d6535a6e818/Images/ChinaUSA.png?raw=true)

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
