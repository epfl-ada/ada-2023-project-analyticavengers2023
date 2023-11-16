# Community evolution on YouTube in Gaming

# Abstract
Communities are at the heart of YouTube. Major communities like _Gaming_ or _Entertainment_ dominate in the YouTube space. In our work, we decide to dive in-depth into the _Gaming_ community and define relevant sub-communities related to the gaming industry. These include a selected set of major games, like _GTA, Minecraft, Fortnite_ and more. We also take a look at other communities dedicated to Mobile Games, such as Clash Royale. Additionally, we consider communities focused on Gaming News, which encompasses channels like IGN. We will analyze these communities based on the engagement of viewers in the comments section. Using the comments' engagement of viewers is a strong assumption for analyzing these communities, as people who write comments tend to be those engaged in the community. Our goal is then to model communities and interactions between different communities over time. For example, how often do people in the _Minecraft_ community comment on _Fortnite_ videos? And how often do users migrate to other communities? We will show that users interact with other communities when events take place, such as the release of _Fortnite_ in 2017, and we will show how and why.

# Research Questions
- How do communities interact, and how do they evolve?
- What are the key factors that could lead to an attention shift from one community to another?
- Are there some games that are resistant to change and have remained stable since 2015?

# Methodology

#### Data Cleaning: 
- Given the immense dataset that YouNiverse represents, we needed to refine the data we wanted to actually work with.
    - Initially, we wanted to study a subset of major communities (like News & Politics), but given the sheer amount of data we would need to work with, we decided to restrict our study to the _Gaming_ videos and define communities as major games.
    - As part of the cleaning, we manually selected relevant communities, mainly as games (like _GTA_). In each community, we also selected channels which were dedicated to these communities. For example, Pewdiepie, who has played many games on YouTube, is not part of any of these communities.
- For now, we keep all authors, but we might filter authors who have a certain amount of comments. This is because users who comment 2 or 3 times in their lives aren't truly part of a community, whereas a user with $100$ comments in gaming videos truly belongs in the gaming community.
- Finally, the only cleaning which was done was to reorganise the data in a meaningful and practical way (e.g., merging dataframes together to capture the relevant information from one dataframe)

#### Community definition and viewer membership
- A community is defined by a major game or is heavily related to _Gaming_. The communities we have defined are mentioned in the abstract (susceptible to changes in P3).

- We will study comments on YouTube between the years 2015 and 2019 (the only years available in the time series data). From comments, can compute the category of videos authors commented on the most and link them to a community. Using the time series data, we can study the comments data for every week and if the majority of the comments users have made in this time window changes over time, they will change community. For instance, if user $u$ has authored 60% of their comments in category $X$ and 40% in category $Y$ at a certain time period $T$, they will be linked to $X$. At time $T+T'$, suppose the proportions become 40% and 60% respectively, then user $u$ will become a member of $Y$.
#### Timeseries analysis
A preliminary analysis was made on the timeseries data to observe the evolution of views and subscribers for the largest channels. However, since we decided to work on _Gaming_ videos, we decided to dive deeper into this YouTube category. We studied the evolution in the timeseries of the specific channels we handpicked and the correlations over time. This will allow us to look at the interactions between communities. We want to measure the outgoing comments from one community to another, if people leave their communities, and if so, __when__ does this happen? More details in __Organization__.

#### Comments Analysis
We first started exploring the distribution of the comments dataset, using comments per video and comments per author. The aim was to gain an overview of the feasibility of using author-specific comments for robust future analysis. Moreover, this is where the selection of specific gaming channels per community were chosen.
We also focused our analysis into video _tags_, matching viewers to videos at a certain point in time. Then, we went more in depth into the _Gaming_ community. From this analysis, we could see that users usually comment in few communities (some examples include users commenting only on Fortnite and Minecraft videos). Note that these preliminary analyses were conducted using a sample of 100 million comments from the extensive comments dataset.
  
# Timeline
Steps:
- For P3, we will have a much more reduced dataset, which will be easier to work with. We still need to confirm which _Gaming_ communities we will end up using in our analysis. For example, the Gaming News community might be less interesting to study.
- Produce a detailed analysis of the evolution of gaming communities over time, aiming to correlate significant shifts with real-world events.
- Build a large directed network, to model the interactions between communities.
    - The aim is to have $n$ nodes, where $n$ denotes the number of communities we work with. The nodes will be designed as bubbles, where the size of the bubbles designates the number of members in that community, which can change over time.
    - The set of weighted edges $E$ will represent the number of comments from the outgoing community to the receiving one, where the weights grow depending on the number of comments between communities. 
      
- Perform a clustering analysis using both comments and tags, steps:
    - extract all gaming videos, identify their main tags, and categorize the set of authors who commented or did not comment. Use dimensionality reduction techniques such as PCA or t-SNE to visualize whether videos naturally cluster by communities.


# Organization
|  Timeseries Analysis    |  Comments Analysis    |  Report and weekly meetings    |
|:-------------------------:|:-----------:|:-------------:|
|  Paul, Yubo, Luca | Adam, Marc-Antoine| ALL|
| __Yubo__ focused on examining the relationship between different metrics, such as subscribers and videos to understand these relationships. __Luca__ made a preliminary analysis on the timeseries, focusing on the largest channels at first and then over more specific Youtube categories.|__Marc-Antoine__ conducted an exploration on the comments dataset. The aim was to gain an overview of the feasibility of using the comments of every author for future analysis. With __Paul__ they collaborated in the selection of the gaming communities and the selection of relevant channels in each community.
|  __Paul__ looked into the evolution in the timeseries of the channels we handpicked and the correlations over time.| __Adam__ initially studied comments for each major Youtube community. Then, zooming into the _Gaming_ community, he analyzed how the community behaved for each game we were interested in.| |
