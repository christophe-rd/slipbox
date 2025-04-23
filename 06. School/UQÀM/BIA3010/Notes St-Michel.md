#statistics #bia3010
[[2023-08-09]]
##### Variables continues ou discrètes.
- Le temps peut être des variables continues ou discrètes.
- Discrètes : couleur, présence/absence.

On veut voir la relation entre x et y. Dépendement des variables, on va dire à R si c'est discret ou continu.
Les modèles linéaires sont prévus pour des résidus qui sont distribués de façon normale. 

Résidu: valeur observée - valeur prédit

Summary of a linear model: 1Q and 3Q are my SD of my gaussian distribution. 

Si j'ai un intercept négatif et que ça n'a pas de sens biologique, je vais les centrer à l'origine. 
On peut avoir un p significatif, mais si le R2 est très faible, ça dit que ma valable n'explique pas qu'une variable. C'est la distinction entre le fait qu'un jeu de donnée soit significatif et la portée biologique. 
- Idéalement, je centre toujours mes données de mon modèle linéaire, parce que ça leur permet d'être comparable.

ANOVA: ma valeur F me dit s'il y a une différence significative entre les trois traitements, incluant le contrôle, mais les valeurs de la table, me donne un traitement par rapport à l'intercept et un autre, aussi par rapport à l'intercept. 

Modèles multivariés:
Modéliser l'abondance de plusieurs espèces dans un même environnement.

[[2023-08-14]]
##### Présentation de Béatrix 


[[2023-08-28]]
Commentaire de Hélène
- Regarder des relations entre les espèces de pics
- Utilisateurs de cavités

Point d'écoute, l'heure est importante. On peut 
Justifier pourquoi on fait fit du stade de dégradation quand l'arbre.

Comment on va analyser l'abondance du pic flamboyant, pimi, etc. Est-ce qu'on fait une analyse multivariée pour l'habitat. Comment 
Calculer le temps supplémentaire que ça prendrait d'ajouter des espèces

Important de finir le protocole


Quantité d'habitat dégradé autour de nos sites. Centre du transect. Tracer un cercle, qu'est-ce qui est dégradé. Estimation visuelle


[[2023-09-10]]
Créer un projet dans R permet d'augmenter la portabilité des scripts, données et outputs, parce que ça contrecarre le WD. Quand je vais ouvrir ce projet, tout va y être.

[[2023-09-11]]
#statistics 
Analyse de variance, qu'est-ce qu'on compare? On compare des valeurs numériques et des variables catégoriques aka facteurs. 
Ce qui reste de la variance, c'est une variance résiduelle, qui correspond à ce qui n'est pas expliqué.

Typiquement, les données discrètes suivent une loi de poisson. Normalement, les distribution normales ont une moyenne qui est au centre. Quand c'est une loi poisson, on peut les logger, et ça devrait tasser nos données vers le centre. 

Le postulat de base d'un modèle est pas que mes données de bases soient distribués de façon gaussienne, mais nos résidus.

F c'est variance intra groupe et intergroupe, beaucoup de variance entre les groupe, mais peu dans les groupes, la valeur F va être petite. nous dit la taille , p nous dit que si y'a un seuil de détection qui est franchit. Plus la vairance intra groupe est grande par rapport à la variance intergroupe, plus mon F va être grand.

Résidus: bruit autout de notre équation, autrement dit, ce qui n'est pas expliqué pas mon modèle. 

[[2023-09-15]]
##### Atelier sur les analyses multivariées
Source: file:///Users/christophe_rouleau-desrochers/Downloads/atelier_multivarie_LA.html
Univariée: une variable réponse qui est une colonne de notre DF. Ici, la multivariée, c'est des vecteurs au sein d'une matrice. 

CA: seulement pour les espèces, ça doit seulement être pour l'abondance des espèces. PCA, ça fonctionne. CA c'est bon pour les doubles zéros (dans le cas ou deux sites ont deux fois absence de deux espèces, ça pourrait les considérer comme des ressemblances, mais c'est pas bon).

avec la fonction cca. Summary de ça, il faut regarder la "proportion explained"
Species score: ça nous donne les coordonnées des espèces sur le graph. Les axes ce ne sont pas des axes biologiques. 

Axes c'est quelque chose qui explique le maximum de la variabilité entre les espèces. L'axe 1 pourrait être la régression entre l'abondance entre espèce A et B. L'axe B pourrait expliquer le reste de la variabilité

envfit, on lui donne la ca et va nous trouver une corrélation avec les données environnementales. 

ACP c'est un sommaire de la variabilité environnementale pour trouver la corrélation entre différente variables qui sont regroupées en une seule variable explicative. 

Si diversité est corrélée avec axe 2 significativement, ça veut dire que les variables les plus loin de l'axe deux sont plus fortement corrélées à la diversité et celle plus proche, un peu moins. 

Selon Pierre Legendre, les mesures de distance, bray curtis, hellinger
**Eucledienne**: mesure de la distance sur 2 axes.
**Hellinger** : donne moins de poids aux espèces rares.
PERMANOVA:
Version multivariée de l'ANOVA.


#### Rencontre individuelle
On aurait pas besoin de prendre en compte la hauteur des arbres avec un ACP, parce que biologiquement ça fait pas de sens. 

5 réplicas par espèce.

Matrice de commmunauté de pics avec une analyse multivariée
Commencer avec une analyse au niveau du transect.
Question: 
- Est-ce que je dois mettre dhp en mettre avant de centrer réduire mes données? 

[[2023-09-18]]
#### Atelier 6:
file:///Users/christophe_rouleau-desrochers/Downloads/data_visualization%20(1).html
Facteur ça prend en compte s'il y a différents niveaux e.g. character et numeric dans la même colonne. On est mieux de convertir en numeric, il va y avoir moins de problème avec les fractions and shits. 

l'annexe devrait contenir des tableaux et des figures qui ne sont pas nécessaire à la compréhension de nos hypothèses/histoire.

Pour les ordinations, on peut retirer des espèces pour faciliter la lisibilité, mais il faut préciser qu'on a seulement garder les espèces avec le score le plus élevé.


faire tableau:
1. juste effet aléatoire
2. un autre avec les effets fixes

Représentation graphique pour tous mes effets fixes


[2023-09-20]
Une échelle au niveau des arbres 
Une échelle au niveau des transects.

Espèce en aléatoire nous donne une variance expliqueé totale par les espèces, mais pas par espèce individuelle. 

Effet fixe: c'est l'effet qu'on veut expliquer la variabilité, effet aléatoire on va les prendre en considération, parce qu'ils expliquent une partie de la variabilité. 

Il faut extraire la variance totale --> à poser aux démos. Au niveau des effets aléatoires seulement. Le mettre dans le tableau final ??
Si y'a des arbres qui on tun dghp différent entre les transects, l'effet aléatoire transect va venir compenser pour ça et va changer la variance.
Variance effet aléatoire espèce. Si espèce de pic préfère x espèce d'arbre, ça peut avoir une relation entre une variable aléatoire et fixe, ça peut augmenter ou diminuer la variance de cet effet aléatoire. 