# Community evolution on YouTube in Gaming

# Abstract
Communities are at the heart of YouTube. Major communities like _Gaming_ or _Entertainment_ dominate in the YouTube space. Viewers who engage with communities they are interested in tend to comment on their videos, these viewers hence belong to the community of these channels. In our work, we decide to dive in depth into the _Gaming_ community, and define relevant sub-communities to the gaming industry. These include a selected set of major games: _Call of Duty, GTA, FIFA, Minecraft, Fortnite, League of Legends_, and other communities dedicated to Mobile Games, such as Clash of Clans. Additionally, we consider communities focused on Gaming News, which encompass channels like Rockstar Games or IGN, publishing videos related to new games, and so on. We will analyze these communities based on the engagement of their authors in their respective comment sections. Using the comments' engagement of the viewers is indeed a strong assumption for analyzing these communities, as people who write comments tend to be those engaged in the life of the channel. Our goal is then to model communities and interactions between different communities over time. That is, how often do people from community $X$ comment on videos of community $Y$? And how often do users migrate to other communities? We will show that users interact with other communities when events take place, such as the release of _Fortnite_ in 2017, and we will show how and why.

# Research Questions
- How do communities interact, and how do they evolve?
- Which community dominates over others?
- What are the key factors that could lead to an attention shift from one gaming community to another?
- Since 2015, how have communities of major games evolved?
- Are there some games that are resistant to change and have remained stable since 2015?

# Methodology

#### Data Cleaning: 
- Given the immense dataset that YouNiverse represents, we needed to refine the data we want to actually work with.
    - Initially, we wanted to study a subset of major communities (like News & Politics), but given the sheer amount of data we would need to work with, we decided to restrict our study to the _Gaming_ videos and define communities as major games.
    - As part of the cleaning, we manually selected relevant communities, mainly as games (like _GTA_). In each community, we also selected channels which were dedicated to these communities. For example, Pewdiepie, whom has played many games on YouTube, is not part of any of these communities.
- For now, we keep all authors, but we might filter authors who have a certain amount of comments. This is because users who comment a 2 or 3 times in their lives aren't truly part of a community, whereas a user with $100$ comments in gaming videos truly belongs in the gaming community.
- Finally, the only cleaning which was done was to reorganise the data in a meaningful and practical way (e.g., merging dataframes together to capture the relevant information from one dataframe)

#### Community definition and viewer membership
- A community is defined by a major game or is heavily related to _Gaming_. The communities we have defined are _Call Of Duty, GTA, Fifa, Minecraft, Fortnite, League of Legends_, _Mobile Games_ and _Gaming News_ (susceptible to changes in P3).

- Given users' comments on YouTube between the years 2015 and 2019 (the only years available in the time series data), we can compute the category of videos they've commented on the most and link them to a community. Comments are very meaningful to assign users to communities. In fact, the users who truly engage with communities are those who comment on videos. Using the time series data, we can study the comments data for every week (or month; TBD) and if the majority of the comments users have made in a certain time window (e.g., 1 month) changes over the years to another category, then this user is linked to the other community. For instance, if user $u$ has authored 60% of their comments in category $X$ and 40% in category $Y$ at a certain time period $T$, they will be linked to community $X$ for the time being. Now, suppose at time $T+T'$, the proportions become 40% and 60% respectively, then user $u$ will become a member of community $Y$.
#### Timeseries analysis
A preliminary analysis was made on the timeseries data $TODOOO$ $Yubo general analysis of the data → Comments on distribution + categories we have ect..$

However, since we decided to work on _Gaming_ videos, we decided to dive deeper into this YouTube category. We studied the evolution in the timeseries of the specific channels we handpicked and the correlations over time. This will allow us to look at the interactions between communities. We want to measure the outgoing comments from one community to another, if people leave their communities, and if so, __when__ does this happen?

#### Comments Analysis
In this section, we discuss the comments analysis which was made. 
We first started exploring the distribution of the comments dataset, using comments per video and comments per author. The aim was to gain an overview of the feasibility of using author-specific comments for robust future analysis. Moreover, this is where the selection of specific gaming channels per community were chosen.
We also focused our analysis into video _tags_, matching viewers to videos at a certain point in time. First, we looked at all the data to observe the amount of comments per Youtube categories. From there, we could quickly conclude users' comments show that they mostly always comment in the same kind of videos. Then, we went more in depth into the _Gaming_ community. There also, we could see from preliminary analysis that users usually comment in few communities (some examples include users commenting only on Fortnite and Minecraft videos). 
Note that these preliminary analyses were conducted using a sample of 100 million comments from the extensive comments dataset. During step 3 of this project, we may increase this number of comments and selectively choose those posted under gaming videos. However, due to the large and challenging size of the file, managing it will be one of our significant challenges.

### Community Graph
- Our aim for the milestone 3, is to build a large directed network, to model the interactions between communities. The aim is to have $n$ nodes, where $n$ denotes the number of communities we decided to work with. The nodes will be designed as bubbles, where the size of the bubbles designates the number of members in that community.
- The set of edges $E$ represents the number of comments from the outgoing community to the receiving one. The idea is to make the edges have weights, where the weights grow when there is a larger number of comments authored in another category.
- We will also modify the size of nodes over time, as members can leave or join the community.

The ultimate goal is to produce the evolution of this graph over time. We want to make an interactive UI, where we can scroll over time and look at how this graph evolves

# Timeline
Steps:
- For P3, we will have a much more reduced dataset, which will be easier to work with. We still need to decide if we will merge some communities together, to get a more accurate representation of communities. For example, one idea we have is to include the game _Pro Evolution Soccer (PES)_, and merge it together with _Fifa_ to form one individual community - _Football_.
- We then need to define a time window (we are thinking about 1 month) to match users to their categories. This way, for every time period $t$, we have a fixed state of the communities in time: we can collect comment data for each user and assign them to a community. $TODO$ needs clarity.
- Produce a detailed analysis of the evolution of gaming communities over time, aiming to correlate significant shifts with real-world events.
- Produce the graph. 
    - As mentioned, we can produce the data to make the graph for every time period we define. The idea would be to have a scrollable graph, able to scroll over each time period and check the state of the communities and the interactions between these.
- Perform a clustering analysis using both comments and tags.
    - The objective would be to extract all gaming videos, identify their main tags, and categorize the set of authors who commented or did not comment. Utilize dimensionality reduction techniques such as PCA or t-SNE to visualize whether, on a global scale, videos naturally cluster by communities (i.e., equivalent tags).


# Organization
|  Timeseries Analysis    |  Comments Analysis    |  Report and weekly meetings    |
|:-------------------------:|:-----------:|:-------------:|
|  Paul, Yubo, Luca | Adam, Marc-Antoine| ALL|
| __Yubo__ and __Luca__ worked on an overall analysis of the timeseries data (e.g., looking into the evolution of views and subscribers or finding patterns)|     __Marc-Antoine__ conducted an exploration of the basic statistics and data distribution of the comments dataset, using two datasets: comments per video and comments per author. The aim was to gain an overview of the feasibility of using author-specific comments for robust future analysis. Additionally, with __Paul__ they collaborated in the selection of gaming channels and conducted a Exploratory Data Analysis (EDA) on the new filtered dataset, which exclusively comprised the chosen gaming channels.
|  __Paul__ looked into the evolution in the timeseries of the specific channels we handpicked and the correlations over time.| __Adam__ highlighted the evolution over time of all the major Youtube communities and put the characteristics of the comments for each community, analysing the link that exists between them. Then, zooming into the _Gaming_ community, he analyzed how the community behaved for each game we were interested in.| |
