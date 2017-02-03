# Modelisation_Guitare

Les fichiers corde.txt sont générés grâce à la modélisation de la corde seule.

Cette modélisation "écoute" la corde en plusieurs points, afin d'homogénéiser l'amplitude du son final. En pratique, on entend la moyenne des mesures effectuées en trois points distincts de la corde. On ne fait qu'une addition car le son final est automatiquement recalibré pour être audible, mais pas saturé dans le fichier sondCreator.py.

Afin d'"accorder" les cordes, j'ai pu modifier la valeur du module d'Young de l'acier qui varie en fonction de la tension de la corde. En testant différentes valeurs, j'ai pu ainsi fixer un module d'Young différent pour chacune des cordes modélisées. Nous ne disposons ici que de quatre cordes parce que la modélisation n'est plus stable pour des valeurs de E trop grandes. Je n'ai donc pas modélisé les deux cordes les plus aiguës de la guitare. Il aurait fallu pour cela modifier la fréquence d'échantillonnage du son (ce qui n'est pas possible ici puisqu'on travaille avec un standard de 44100Hz) ou le nombre de points de la discrétisation de la corde.

N'ayant pas lié les cordes à la table d'harmonie, j'ai pu modéliser les accords dans le fichier 4cordes.py. Le son produit par chacune des quatre cordes séparément est traité de manière indépendante, et donc simplement additionné puis réécrit dans un fichier txt qui sera utilisé dans soundCreator.py.

Pour ce qui est du morceau, j'avais d'abord pensé à retranscrire le début de la partition de la marche turque de Mozart, mais les notes jouées à la main droite du piano sont trop aiguës. N'ayant que les quatre cordes les plus graves, il fallait pouvoir jouer plusieurs octaves sur une même corde, ce qui ne rend rien de bon, à cause du fait que le nombre de points pour la discrétisation de la corde est limité. En effet, on ne peut augmenter le nombre de points de manière conséquente en restant à une fréquence d'échantillonnage de 44100Hz, sansque le modèle ne devienne instable. Le peu de points utilisé rend ainsi le placement du doigt sur la corde trop approximatif, et la note jouée est trop fausse pour être agréable à l'oreille.
Je suis donc parti sur frère Jacques, avec des notes plus graves, et plus justes.
