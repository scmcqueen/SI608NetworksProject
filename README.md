# SI608NetworksProject
Final Project for SI608 Networks
Luna, Mariam, Julia, & Skyeler

[Check out our presentation!](https://docs.google.com/presentation/d/1q4EkyI7FGm7iJJC98Zel_1H-WaVw63EMZ8qNU2nXE2Y/edit?usp=sharing)

### Files
- **SpotifyApiFunctions.ipynb**: This file is used to query the data from Spotify. If you want to run it, you will need your own Spotify API token.
- **LoadGraph_Example.ipynb**: In this file, we load one example of the graphs and visualize it using nx altair.
- **LoadFullGraphs.ipynb**: IN this file, we turn the json files of the network into more convenient pandas df & conduct a network analysis.
- **ML_in_playlist_nodeEmbeddings.ipynb**: This file creates the ML model with node embeddings from the graph.
- **ML_analysis.ipynb**: This file creates ML models with & without network features to compare.
- **gnn.ipynb**: In this file, the graph nueral networks are created and executed.
- **community_detection.ipynb**: In this file, we complete clique percolation community detetction for our networks.

### Data Files 
- **old_data**: (folder) data from the Instagram Reels playlist, but with only 20 collaborators per artists & no random seed data. None of this data was used in our models; it was an earlier attempt at querying.
- **week1.csv, week2.csv, week3.csv**: These csvs contain the node information for each of the three graphs. E.g. for Sabrina Carpenter it has her source (playlist query), popularity, followers, collaborators, etc and the network features (pagerank, closeness centrality, etc.).
- **MM_DD_playlist_layerX.json, MM_DD_random_Xlayer.json**: These jsons have the data directly from the Spotify queries.
- **cache.json**: Cache with query information per each artist to increase the speed of the query process.
- **ml_dataset.csv & ml_dataset_2.csv**: Datasets that are cleaned for machine learning.
- **community_percolation_results.csv**: Results from the community percolation.
- **final_xgb_model_with_smote.pkl & final_xgb_model_with_smote_new_data_new_data.pkl**: ML models with & without network data.
- **tuned_rf_with_smote.pkl**: Random forest model augmented with smote.
- **EDA_Network_Analysis**: File with some EDA on the data.

We tried four different methods for predicting which artists will are in the “Instagram Reels - Top Trending 2024 | NEW VIRAL HIT SONGS ON THE INTERNET” playlist from a network generated with nodes from the playlist, a selection of randomly selected nodes, and their first and second degree collaborators. We wanted to see if using the network collaboration features would be a better way to predict an artist’s success than predicting success based on Spotify features like popularity and followers. Of all the methods we tried, we found that using a random forest machine learning model with node embeddings was the best performing solution (f-1 score of 0.980), compared to a machine learning model without graph information, a machine learning model with graph information (page rank, clustering, etc.), clique percolation community detection, and a graph neural network. This shows that collaboration network information is a helpful feature for predicting which artists will  be popular on Instagram, when combined with other ML features.
