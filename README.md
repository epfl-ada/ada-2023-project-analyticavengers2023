# Community evolution on YouTube

### Abstract
Communities are at the heart of YouTube. Major communities like gaming or entertainment dominate in the YouTube space. Viewers who like to interact with the channels they like tend to comment on their videos, these viewers hence belong to the community of these channels. In our work, communities are defined by video categories (e.g., gaming or sports) and viewers belong to a community $X$ if they have authored more than TODO comments, with the majority of comments belonging to videos in category $X$ at a certain point in time. Our goal is to model communities and interactions between different communities over time. That is, how often do people from community $X$ comment on videos of the community $Y$? And how often do users migrate to other communities? Our aim is to show that users interact with other communities when major events take place, and we will show how and why.

### Research Questions
- How do communities interact and how do they evolve?
- Which community dominates over others?

### Methodology

#### Data Cleaning: 
- Given the immense dataset that YouNiverse represents, we needed to clean the data to refine the data we want to actually work with.
- For this we decided to work on a subset of communities, namely: $A, B,C,D TODO!!$
- We also decided to work with channels who had over $TODO$ subscribers. That is because channels with a lower number of subscribers do not have _strong_ communities behind them.
- Furthermore, we decided to keep only authors who had over $TODO$ comments in their history. This is because users who comment a dozen times in their lives aren't truly part of a community, whereas a user with $1000$ comments in gaming videos truly belongs in the gaming community.
- ANYTHING ELSE?? $TODO$

#### Community definition and user membership
- A community is simply the categories of youtube videos. 
- Given users' comments on YouTube between the years 2015 and 2019 (the only years available in the time series data), we can compute the category of videos they've commented on the most and link them to a community. Using the time series data, we can do this for every week (or month; TBD) and if the majority of their accumulated comments over the years changes to another category, then this user is linked to the other community. For instance, if user $u$ has authored 60% of their comments in category $X$ and 40% in category $Y$ at time $t$, they will be linked to community $X$ for the time being. Now, suppose at time $t+t'$, the proportions become 40% and 60% respectively, then user $u$ will become a member of community $Y$.

#### Community Graph
- Our aim for P3, is to build a large directed network, to model the interactions between communities. The aim is to have $n$ nodes, where $n$ denotes the number of communities we decided to work with. The nodes will be designed as bubbles, where the size of the bubbles designates the number of members in that community.
- The set of edges $E$, with $|E|=n(n-1)$ represents the number of comments from the outgoing community to the receiving one. The idea is to make the edges have weights, where the weights grow when there is a larger number of comments authored in another category.
- We will also reduce the size of nodes if we see a community migration of users.

The ultimate goal is to produce the evolution of this graph over time. We want to make an interactive UI, where we can scroll over time and look at how this graph evolves

### Timeline
For P3, we want 
