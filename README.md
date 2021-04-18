# Introduction
Projet IAS (Introduction Apprentissage Statistiques) Université Paris-Saclay

# Les Données

## Features musicales

* acousticness (Ranges from 0 to 1) 
= Est-ce que la musique est codifiée par des règles mathématiques 
(et peut donc s'écrire sous forme d'une partition) ?
* danceability (Ranges from 0 to 1) 
= Est-ce que la musique donne envie de danser ?
* energy (Ranges from 0 to 1)
= Est-ce que le morceau est énergique (ex : Hard Rock > Prélude Bach)
* duration_ms (Integer typically ranging from 200k to 300k)
* instrumentalness (Ranges from 0 to 1)
= Est-ce que le morceau est uniquement instrumental (ne contient pas de paroles) ?
* valence (Ranges from 0 to 1)
= Est-ce que le morceau est joyeux (1.0) ou triste (0.0) ?
* popularity (Ranges from 0 to 100)
= Pourcentage entier de la popularité calculée selon le nombre d'écoutes
et si ces écoutes sont récentes, calculé par un algorithme qui est une
boîte noire
* tempo (Float typically ranging from 50 to 150)
= Nombre de pulsations par minute
* liveness (Ranges from 0 to 1)
= Est-ce que le morceau a été enregistré en live avec un public ?
* loudness (Float typically ranging from -60 to 0)
= Atténuation de l'intensité sonore globale (en dB), 0 dB correspond à l'intensité
théorique maximale
* speechiness (Ranges from 0 to 1)
= Est-ce que le morceau contient beaucoup de paroles ?
* year (Ranges from 1921 to 2020)

## Features catégorielles

* mode (0 = Minor, 1 = Major)
= Le mode dépend de l'armature de la partition et va créer l'atmosphère
de la musique (joyeux pour majeur, triste pour mineur)
* explicit (0 = No explicit content, 1 = Explicit content)
* key (All keys on octave encoded as values ranging from 0 to 11, starting on C as 0, C# as 1 and so on…)
= Quelle est l'armature de la partition (ie: le nombre de dièses ou de bémols cela donne la tonalité) ?
* artists (List of artists mentioned)
* release_date (Date of release mostly in yyyy-mm-dd format, however precision of date may vary)
* name (Name of the song)

# Pré-Processing

* Supprimer id, name, realease date 
* Changer l'echelle de duration_ms
* Supprimer les chansons trop impopulaires
* supprimer les chansons realisées par les 4 artistes avec le plus de chansons
* Binariser speechiness et instrumentaleness
* Modifier artist pour mesurer la popularité moyenne de chaque artiste
* Supprimer les données dupliquées
