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

Pour ce faire, nous avons repris le code vu en cours pour détecter les punch : https://github.com/walid213/tinyml-workshop

Nous avons générer les fichiers "oui.csv" et "non.csv" pour les 2 différents gestes. 
En entraînant l'IA, on obtient le fichier "model.h" que nous allons utiliser pour détecter les gestes.

On rajoute ensuite les commandes d'affichage des questions et on attend les réponses avec les gestes.

Résultat à l'aide de MobaXterm :

![result projet 1](https://user-images.githubusercontent.com/92917769/211164339-4de452c0-6905-4d04-9a65-2d6906d25cee.png)

Tout fonctionne correctement.

# Projet 2

Nous avons commencé par enregistrer les échantillons des prononciations des différents mots sur Edge Impulse.

Nous avons ensuite ajouté les blocks de training et de test.

Nous avons lancer l'entraînement et obtenu les résultats suivants :

![image](https://user-images.githubusercontent.com/92917769/211169935-aa7684cf-ff2e-478c-9da5-d2f896e7fbff.png)
![image](https://user-images.githubusercontent.com/92917769/211169945-396987fd-cf97-41c4-a0bc-c467e5edc517.png)
![image](https://user-images.githubusercontent.com/92917769/211169949-2187e0b1-3c86-43e7-a460-7676b5837d8a.png)

Nous avons ensuite effectué les tests sur le model que nous avons créé : 

On reteste le model pour connaitre son efficacité :

Nous avons commencé par dire "FPGA" :

![image](https://user-images.githubusercontent.com/92917769/211169983-d4485de6-4245-47b6-ab67-7859ed39b6e8.png)
![image](https://user-images.githubusercontent.com/92917769/211169991-ac0bef71-7691-4973-96e2-bf4589a2d15f.png)
![image](https://user-images.githubusercontent.com/92917769/211169996-f90249de-ac3b-4831-a02b-65cd7e5cda2c.png)

Le model fonctionne bien et détecte bien "FPGA".

Nous avons ensuite testé avec "microcontrôleur" : 

![image](https://user-images.githubusercontent.com/92917769/211170022-5a5c4f12-f6c9-4e9d-9a7f-3ba9446fd07f.png)
![image](https://user-images.githubusercontent.com/92917769/211170025-e32a2a85-2db3-443d-b7cb-adee65c214c9.png)

Encore une fois, le model détecte bien le bon mot. La détection est d'ailleurs encore plus efficace.

Nous avons ensuite build l'ensemble du dispositif et nous avons flashé notre carte arduino avec le fichier téléchargé.

Nous nous sommes arrêté ici pour le moment. 
