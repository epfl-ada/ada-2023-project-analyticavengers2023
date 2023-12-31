# Fortnite on YouTube: A Success Story 🥇

Our [data story](https://epfl-ada.github.io/ada-2023-project-analyticavengers2023/#top) 📖

# Abstract
In this stage of our research, we delve deeper into the complex dynamics of gaming communities on YouTube, focusing particularly on the transformative impact of Fortnite. This game has not only revolutionized the battle-royale genre, but has also significantly influenced the structure and behavior of gamer communities on YouTube. Our analysis aims to understand how the introduction of Fortnite and the evolution of its features have altered viewer engagement patterns, community interactions and content creation trends on the platform. In addition, we address the wider implications of Fortnite's influence, including its role in mainstream pop culture and its contributions to emerging issues such as online harassment in gaming spaces. Our aim is to present an overview of how a single game like Fortnite can act as a catalyst in shaping the landscape of digital communities, influencing both virtual and real-world interactions. 
# Research Questions
<ul>
                    <li>How did this new game engineering (open world vs. battle royale) and business model upset the classic game industry?</li>
                    <li>Did Fortnite attract pre-existing gamer YouTubers, or were Fortnite creators newcomers to the platforms?</li>
                    <li>Did Fortnite attract viewership from established gaming communities, or did it build its own distinct audience?</li>
                    <li>Do active authors who engage in extensive commentary participate in a singular community, or do they contribute to various communities across different games?                       </li>
                    <li>How Fortnite transformed various aspects well beyond the confines of the gaming industry?</li>
                    <li>How did established games like Minecraft withstand the impact of a successful release like Fortnite?</li>


</ul>

# Methodology

#### Data Cleaning: 
- Given the immense dataset that YouNiverse represents, we needed to refine the data we wanted to actually work with.  
    - Initially, we wanted to study a subset of major communities (like News & Politics), but we decided to restrict our study to the _Gaming_ videos and define communities as major games.
    - As part of the cleaning, we manually selected relevant communities, mainly as games (like _GTA_). In each community, we also selected channels which were purely dedicated to these communities.
- Finally, the only cleaning which was done was to reorganise the data in a meaningful and practical way (e.g., merging dataframes together)

#### Community definition and viewer membership
- A community is defined by a major game or is heavily related to Gaming. 
- We studied comments on YouTube and from these, we computed the category of videos authors commented on the most and linked them to a community. Using the time series data, we studied the comments data for every week, and if the majority of the comments users made in this time window changed over time, they changed community. For instance, if user $u$ authored 60% of their comments in category $X$ and 40% in category $Y$ at a certain time period $T$, they were linked to $X$. At time $T+T'$, suppose the proportions became 40% and 60% respectively, then user $u$ became a member of $Y$.
  
#### Timeseries analysis
A preliminary analysis was conducted on the timeseries data to observe the evolution of views and subscribers for the largest channels. However, as we decided to focus on Gaming videos, we delved deeper into this YouTube category. We explored the evolution in the timeseries of the specific channels we selected and examined the correlations over time. This enabled us to examine the interactions between communities. Our goal was to measure the outgoing comments from one community to another, identify instances of people leaving their communities, and determine when these transitions occur.
We also utilized time series data to assess and observe real events as they occurred and their effects on the audience of YouTube channels related to these events. Time series data proved to be a valuable source, coupled and merged with the channel dataset, to address questions related to the join date or celebrity status of YouTubers.

#### Comments Analysis
We then started exploring the distribution of the comments dataset, like stated above, using comments per video and comments per author. The aim was to gain an overview of the feasibility of using author-specific comments for robust future analysis. Moreover, this is where the selection of specific gaming channels per community were chosen.
We also focused our analysis into video _tags_, matching viewers to videos at a certain point in time. Then, we went more in depth into the _Gaming_ community. From this analysis, we could see that users usually comment in few communities (some examples include users commenting only on Fortnite and Minecraft videos). Note that these preliminary analyses were conducted using a sample of 100 million comments from the extensive comments dataset.
We sorted the videos by tags of interest to us, i.e. games: Minecraft, Fortnite, Fifa, GTA, League of Legends ...
We tracked each author, analyzing how and when he switched his interest from one game to another by seeing where he commented and where he came from (which game he had commented on before). Then we stored this information in the form of migration by date.
Finally, we produced a graph that explicitly illustrated the transitions from one game to another.
We also analyzed each game's share of community engagement, using pie charts.
And we produced a graph showing the evolution of each game's community by the number of comments in videos tagged with that game, to demonstrate Fortnite's clear dominance after its release. 
# Timeline

- **5/12/2023**: Define how we will track authors to have the migrations scheme & Create the dictionary of migrations per date
- **10/12/2023**: Create a Graph to illustrate migrations & create and edit a video using the graph created to animate the heart of our research topic
- **15/12/2023**: Have an Office Hour with Dr. Ribeiro to check if our ideas and our vision of the data story is matching the course’s expectations.
- **17/12/2023**: Create Data Visualisations (Pie Charts & Histograms) to show Fortnite’s Dominance
- **18/12/2023**: Data Story, Page Design, and ReadME


# Organization
Team Organisation
- **Yubo** : Implemented the graphs and researched on the YouTube gaming industry from a general perspective, data story of pre-Fortnite era
- **Marc-Antoine** : Implemented the graph on timeseries, data story redaction
- **Paul** : Implemented the graph on timeseries, correlations and youtubers, data story redaction, research on Fortnite in general for data story opening
- **Luca** : Implemented the migrations graph, introduction to the data story and youtube gaming history.
- **Adam** : Video Editing, Migrations Graph, Games’ communities engagements through time, Games & Communities Pie Charts, ReadMe
