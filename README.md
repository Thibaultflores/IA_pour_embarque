# IA_pour_embarque
Projet de la matière IA pour l'embarqué.

Ce projet à été réalisé en binôme avec Thibault FLORES. 

Il s'est avéré que l'une de nos deux carte a cessé de fonctionner lors du developpement des projets, d'où la nécessité de les effectuer en binôme. 

L'erreur était la suivante :
![image](https://user-images.githubusercontent.com/92917769/211161190-72c31a7f-b250-4b0f-86ab-65eae2a4e967.png)
Elle apparassait à chaque upload et aucune de mes tentatives de résolution n'a permis de régler le problème, pas même changer de PC. 

# Projet 1
Pour ce premier projet, il s'agit de répondre à des questions par des gestes d'aprobation et de négation. 
Les questions seront posées via le serial monitor de l'arduino sur lequel nous allons travailler et les gestes seront enregistrés par les différents capteurs (centrale inertielle) présents sur la carte. 

Pour répondre "oui", nous avons choisi d'effectuer un geste de haut en bas, et pour dire "non", nous avons décider d'effectuer un geste de droite à gauche. 

La première étape consiste à enregistrer les deux gestes dans une base de données afin que l'IA s'entraîne à les reconnaître. 

Nous allons ensuite lancer l'entraînement de l'IA et allons coder quelques lignes permettant de poser les questions via le serial monitor et de répondre en reconnaissant les deux gestes. 

Pour ce faire, nous avons repris le code vu en cours pour détecter les punch.

Nous avons générer les fichiers "oui.csv" et "non.csv" pour les 2 différents gestes. 
En entraînant l'IA, on obtient le fichier "model.h" que nous allons utiliser pour détecter les gestes.

On rajoute ensuite les commandes d'affichage des questions et on attend les réponses avec les gestes.
