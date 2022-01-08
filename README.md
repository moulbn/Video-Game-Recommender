# VIdeo Game Recommender
Recommending the finest video games to the finest of nerds

This repository documents the pipeline and database enginereed for video games recommendation. Three types of content are recorded: 
- the structured database "steam-200k.csv", which is downloaded from the open-source Steam database and namely reused on Kaggle (@Tamber, last update on 2017 via https://www.kaggle.com/tamber/steam-video-games/data)
- the .ipnyb file "preprocessing_baseline.ipnyb" which performs preprocessing on the data
- the .ipnyb file "final_recommender.ipnyb" which launches the final model tuned on the data

For an end-to-end implementation of the recommender algorithm, the user may follow the suggested workflow: 
1) load the dataset from the data folder in the data_prep branch

2) download and launch the C++ builder tool Visual Studio installer

3) dowload and run the preprocessing.ipnyb file

4) download and run the final_recommender.ipnyb file 

In particular, the preprocessing file computes a quantitative "score" variable,
conditioned on the time a player spent on their purchase game, or the fact that he/she/they
only purchased the game.

A weighted version of that score is then used as an output of TMDB toy-model, using
the 95th percentile as an arbitrary cutoff for the the minimum number of scores required to be listed in the chart

Univariate descriptive statistics are provided for the raw average score per game variable.

In total, 17 183 gamers' information are recorded on the qualified database.

Finally, three recommendation algorithms are cross-validated and compared, namely
the Single Value Decomposition Algorithm i.e. SVD, the K-Nearest-Neighbors Baseline Algorithm i.e., KNN and 
the Product Matrix Factorization Algorithm i.e. PMF, which is a generalized version of the SVD.
