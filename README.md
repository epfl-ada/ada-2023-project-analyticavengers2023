# Community evolution on YouTube in Gaming

# Abstract
Communities are at the heart of YouTube. Major communities like gaming or entertainment dominate in the YouTube space. Viewers who like to interact with the channels they like tend to comment on their videos, these viewers hence belong to the community of these channels. In our work, we decide to dive in depth into the _Gaming_ community, and define relevant sub-communities to the gaming industry. These include: _Call Of Duty, GTA, Fifa, Minecraft, Fortnite, League of Legends_ and other communities dedicated to _Mobile Games_, such as Clash of Clans, as well as _Gaming News_ which encompasses channels such as Rockstar Games or IGN which publish videos related to new games and so on. Viewers belong to a community $X$ if they have authored more than $TODO$ comments, with the majority of comments belonging to videos in category $X$ at a certain point in time. Our goal is to model communities and interactions between different communities over time. That is, how often do people from community $X$ comment on videos of community $Y$? And how often do users migrate to other communities? Our aim is to show that users interact with other communities when events take place, such as the annual release of _Fifa_ games in September, and we will show how and why.

# Research Questions
- How do communities interact and how do they evolve?
- Which community dominates over others?

# Methodology

#### Data Cleaning: 
- Given the immense dataset that YouNiverse represents, we needed to clean the data to refine the data we want to actually work with.
    - Initially, we wanted to study a subset of major communities (like News & Politics), but given the sheer amount of data we would need to work with, we decided to restrict our study to the _Gaming_ videos and define communities as major games.
- We also decided to work with channels who had over $TODO$ subscribers. That is because channels with a lower number of subscribers do not have _strong_ communities behind them.
- Furthermore, we decided to keep only authors who had over $TODO$ comments in their history. This is because users who comment a dozen times in their lives aren't truly part of a community, whereas a user with $1000$ comments in gaming videos truly belongs in the gaming community.
- ANYTHING ELSE?? $TODO$

#### Community definition and viewer membership
- A community is defined by a major game or is heavily related to _Gaming_. The communities we have defined are _Call Of Duty, GTA, Fifa, Minecraft, Fortnite, League of Legends_, _Mobile Games_ and _Gaming News_.

- Given users' comments on YouTube between the years 2015 and 2019 (the only years available in the time series data), we can compute the category of videos they've commented on the most and link them to a community. Using the time series data, we can do this for every week (or month; TBD) and if the majority of the comments they have made in a certain time window (e.g., 1 month) changes over the years to another category, then this user is linked to the other community. For instance, if user $u$ has authored 60% of their comments in category $X$ and 40% in category $Y$ at in a certain time period $T$, they will be linked to community $X$ for the time being. Now, suppose at time $T+T'$, the proportions become 40% and 60% respectively, then user $u$ will become a member of community $Y$.
#### Timeseries analysis
A preliminary analysis was made on the timeseries data $Yubo general analysis of the data → Comments on distribution + categories we have ect..$

However, since we decided to work on _Gaming_ videos, we decided to dive deeper into this YouTube category.
- In our work, we will focus on two main studies.
    - In the first one, we handpick channels manually from each community and look at the interactions between communities. We want to measure the outgoing comments from one community to another, if people leave their communities, and if so, __when__ does this happen?
    - The second study encompasses all of the _Gaming_ videos, which match with the filters imposed in the __Data Cleaning__ section.
    
    In this section, only the First study is relevant.
$Paul part 1 Analysis of several aspect of the evolution of channels in general → Conclusion in general all communities evolve similarly migh be better to be more precise$

#### Comments Analysis
In this section, the second study is more relevant. In fact, the main component of this study has been to look at video _tags_ and match viewers to videos at a certain point in time $ADAM TODO$

#### Community Graph
- Our aim for P3, is to build a large directed network, to model the interactions between communities. The aim is to have $n$ nodes, where $n$ denotes the number of communities we decided to work with. The nodes will be designed as bubbles, where the size of the bubbles designates the number of members in that community.
- The set of edges $E$ represents the number of comments from the outgoing community to the receiving one. The idea is to make the edges have weights, where the weights grow when there is a larger number of comments authored in another category.
- We will also modify the size of nodes over time, as members can leave or join the community.

The ultimate goal is to produce the evolution of this graph over time. We want to make an interactive UI, where we can scroll over time and look at how this graph evolves

# Timeline
Steps:
- For P3, we will have a much more reduced dataset, which will be easy to work with. We still need to decide if we will merge some communities together, to get a more accurate representation of communities. For example, one idea we have is to include the game _Pro Evolution Soccer (PES)_, and merge it together with _Fifa_ to form one individual community.
- We then need to define a time window (we are thinking about 1 month) to match users to their categories. This way, for every time period $t$, we have a fixed state of the communities in time: we can collect comment data for each user and assign them to a community. $TODO$ needs clarity
- Produce the graph. 
    - As mentioned, we can produce the data to make the graph for every time period we define. The idea would be to have a scrollable graph, able to scroll over each time period and check the state of the communities and the interactions between these.

# Organization
|  Timeseries Analysis    |  Comments Analysis    |  Report and weekly meetings    |
|:-------------:|:-------------:|:-------------:|
|  Paul, Yubo, Luca | Adam, Marc-Antoine| ALL|
| __Yubo__ and __Luca__ worked on an overall analysis of the timeseries data (e.g., looking into the evolution of views and subscribers or finding patterns)| __Marc-Antoine__ looked at the comments data for the selected channels for each community ($TODO$), observing the 'trends' over time (e.g., comments related to Fortnite channels like _Ninja_ exploded in 2017 after the release of the game)
|  __Paul__ looked into the evolution in the timeseries of the specific channels we handpicked and the correlations over time.| __Adam__ worked on the comments over all _Gaming_ videos, after the initial filtering process (e.g., channels with over $TODO$ subscribers.) and found meaningful patterns $TODO$ COMPLETE AND MENTION THE DATASETS YOU HAVE PRODUCED| |
