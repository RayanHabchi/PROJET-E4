# PROJET-E4 Système de recommandation de playlists
Bienvenue !

## Objectifs

Ce projet à pour objectif la création d'un système de recommandation de playlists, qui prend une playlist donnée en entrée et recommande une playlist similaire crée par un autre utilisateur. Ce projet ne comprend pas d'interface utilisateur car les systèmes et fonctions développées ont pour but l'intégration dans une application. Cependant, afin de guarantir une bonne lisibilité, nous avons utilisé des notebook python.

## Description

Le notebook 'Saved Song Playlist' permet de récupérer la liste des chansons likés d'un utilisateur (à partir de son client_id de l'api Spotify), puis récupère les features de ces chansons. A partir d'une liste de chansons, on pourra ensuite créer une playlist de taille variable composée de chansons similaires directement dans la bibliotèque de l'utilisateur.

Le notebook 'Dataset_Preparation' contient le code de préparation des données. On y nettoie le dataset 'spotify_dataset.csv'.
On retire toutes les lignes indésirables (doublons, valeurs nulles...), supprime les playlists trop petites, puis on renomme certaines playlists. En effet toutes les playlists 'likés' de chaque utilisateurs avaient le même nom de playlist 'starred'. On a donc renommé ces playlists en fonction de l'id de l'utilisateur afin de les différencier. On récupère ensuite, pour chaque chanson du dataset, ses features avec l'API de spotify. On exporte toutes ces données en un csv 'prepared_data'.

Le notebook 'Recommandation_Model', utilise les données préparées précédement. On répartie les playlists dans des clusters selon leur features. A partir de leur répartition, on peut estimer leur similarité. On crée également un modèle de recommandation aléatoire afin de comparer ses recommandations de playlists à celle de notre système, qui estime la playlist la plus proche d'une playlist donnnée. L'utilisation de clusters crée à partir des features permet d'abolir la barrière des genres et donner des recommandations plus pertinentes. On teste ensuite la précision de notre modèle.

## Utilisation

Afin de reproduire la création de notre système, vous devez:
    - Créer un compte développeur Spotify afin de récupérer votre Client_id et Client_secret (utilisés pour la connection à l'api)
    - Entrer votre Client_id et Client_secret dans les fichiers 'Saved Song Playlist' et 'Dataset_Preparation'.

Tafa SAKHO, Rayan HABCHI, Liantsoa RASOLOMANDIMBY

## Sources
Dataset de playlists :
https://www.kaggle.com/datasets/andrewmvd/spotify-playlists/data?select=spotify_dataset.csv

Librairie Spotify de recherche du plus proche voisin :
https://engineering.atspotify.com/2023/10/introducing-voyager-spotifys-new-nearest-neighbor-search-library/?utm_medium=social&utm_source=linkedIn&utm_campaign=Voyager&utm_content=Evergreen

Video aide API Spotify : 
https://youtu.be/c5sWvP9h3s8?si=WWo60Gg53NNc_U99
