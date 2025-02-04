## Comment poser des pixels de façon optimal.

# Qu'est ce que R/place:

R/place est un projet social où les utilisateurs de Reddit peuvent placer un pixel de couleur sur une toile virtuelle toutes les cinq minutes. L'édition la plus récente de R/place s'est déroulée en Juillet 2023 pendant une semaine entière. L'objectif était de collaborer avec d'autres utilisateurs pour créer des images ou des motifs sur cette toile. Cependant, étant donné que la toile était ouverte à tous et que chaque pixel était modifiable, cela a souvent conduit à des guerres de pixels où les utilisateurs s'affrontaient pour défendre ou modifier certaines parties de l'image. On pourrait citer la "guerre" entre la france et le reste du monde pendant l'édition 2022 de R/place.

-Timelapses des différentes éditions de R/place

2017: https://www.youtube.com/watch?v=XnRCZK3KjUY

2022: https://www.youtube.com/watch?v=K5O3UgLG2Jw

2023: https://www.youtube.com/watch?v=xjOMPka5WFo

Drapeau français sur le canvas en 2022: https://www.youtube.com/watch?v=vjx61CONYww

Charte de l'organisation de l'Allemagne sur R/place: https://www.reddit.com/r/Damnthatsinteresting/comments/txbbne/german_created_a_workflow_chart_for_their_rplace/

Il n'y a pas que des guerres de communautés sur R/place mais également des communautés qui font de jolies choses;

Par exemple:

Une reproduction de _La Ronde de nuit_ par Rembrandt 

<img width="319" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/e6fdfcce-9d20-4d42-be19-802b47733f95">

Il y a même des animations qui sont réalisées au fur et à mesure de la semaine par des groupes organisés et dévoués posant leurs pixels à tour de rôle:

Une reproduction du clip musical Bad Apple: https://www.youtube.com/watch?v=21wfYqPUf-s

Une reproduction de la boucle de gameplay du jeux Outer Wilds, on se reveille près d'un feu de camp, on explore, une étoile explose, on retourne dans le temps et on se reveille près de notre feu de camp: https://www.reddit.com/r/place/comments/15a7li0/routerwilds_animation_sound_collab_timelapse_a/

Maintenant on pourrait se dire que contre un groupe ayant 2 fois plus de membres il est ipossible de s'imposer et de créer une image sur la toile, à défault de se faire recouvrir et écraser. Mais est ce vraiment le cas?

# Peut on gagner face à un groupe avec un avantage numérique?:

Nous avons créé une simulation de la toile du R/place où l'on observe deux groupes d'agents avec des caractéristiques différentes tentant de réaliser une image différente chacun sur la même toile. 

Pour cela, chaque groupe est caractérisé par 4 paramètres: le nombre de personnes dans le groupe, le temps entre chaque pixel posé par les individus moyen, un pourcentage de chance de placer un bon pixel au bon endroit et une couleur.

Il est évident que le nombre de personnes dans un groupe influe sur sa capacité à dessiner efficacement et rapidement ou non. Le temps entre chaque pixel représente si un individu place un pixel dès qu'il peut le faire ou alors ne fais pas vraiment attention et place un pixel un peu quand il en a envie.

Sur une toile vide il est compliqué de coordonéer un groupe très grand. Il est compliqué de de poser un pixel à l'endroit exact. Pour palier à ça, certaines communautées ont crées des calques qui affiche à l'écran l'endroit exact où il faut poser un pixel. Cela permet de réduire les chances de placer un pixel au mauvais endroit.

<img width="540" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/daff7b0d-e73f-44ec-840d-9d916eb1327d">
<img width="332" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/bb18024d-fb84-447c-b1d1-b9cbb3b43c69">

Il y a beaucoup d'autre manière d'augmenter ses chances de ne pas poser de mauvais pixel comme par exemple raffraichir la page avant de poser un pixel.

On notera que les communautés Osu! et Touhou avaient des graphes et des calques qui s'updataient en temps réel: https://www.reddit.com/r/place/comments/156zpm4/for_the_people_accusing_bad_apple_of_using_bots/

Pour notre simulation le groupe 1 aura 100 agents, un temps moyen entre chaque pixel de 5 minutes, 90% de chances de poser un pixel correct et posera des pixels rouges. Le groupe 2 aura 200 agents, un temps moyen entre chaque pixel de 7 minutes, 50% chances de poser un bon pixel et posera des pixels verts. Donc on va faire affronter un groupe composé de 100 personnes très organisé contre un groupe 2 fois plus nombreux mais moins organisé. L'objectif de chaque groupe est de remplir entièrement le canvas de leur couleur.

# Fontionement de la simulation:

Il y a un dictionnnaire qui a un str associé une liste.

<img width="623" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/121b6a91-4c39-4b07-bdca-169e58ecd791">

Il y a des fontions qui renvoient un pixel (une coordonée de la matrice) et mettent à jour le dictionnaire.

Et la fontion pour simuler fait appel aux deux fontion précédentes. D'abord il prend un float compris entre 0 et 1 et le compare à correct_chance (qui est une valeur aussi comprise entre 0 et 1), si le float choisis est inférieur à correct_chance on place un bon pixel, sinon on place un mauvais pixel. Pour les mauvais pixels, on a décidé de modéliser cette "erreur" par la repeinte de la meme couleur d'un pixel déja au bon endroit pour simuler que la personne "gaspille" son pixel.

# Résultat:

Après avoir lancé la simulation on trouve:

Les courbes du taux de complétion en fontion du temps pour le groupe 1 et le groupe 2:

![output](https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/a53bf6fe-9d0e-4f8a-81be-77e2f981ec15)

Gifs de la simulation:

![gif](https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/239a5ff0-0c0f-44c8-aaf9-53483856f966)

Le canvas à la fin de la simulation:

<img width="149" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/a593c811-d5b2-499a-acab-9567f23cb0a1">

On voit que malgré leur inférioté numérique le groupe 1 l'emporte largement sur le groupe 2. Il est donc possible de l'emporter face à un groupe avec un avantage numérique.

# Correct chance optimal:

Le groupe 1 a 90% de chance de poser un bon pixel, ce qui est beaucoup et peu réaliste. Est-ce-qu'avec un correct chance plus bas, il l'emporte tout de même? Pour répondre à cette question, on fixe toutes les variables du groupe sauf correct_chance qu'on fait varier avec un pas de 0.1, et on prend la valeur la plus petite de correct_chance pour laquelle le groupe 1 l'emporte tout de même. En tâtonant on trouve:

Pour correct_chance_g1 = 0.7:

![output](https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/a312865a-a2a5-421a-a239-160c102e4d4f)

Pour correct_chance_g1 = 0.8:

![0 8](https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/c76538cb-6946-4815-8262-a7455f618007)

Il n'est donc pas nécessaire d'avoir 90% chances de poser un bon pixel contre un groupe deux fois plus nombreux, 80% suffit.

# A partir de combien de personnes le groupe 2 gagne?:

Pour un groupe 2 avec 100 personnes:
<img width="176" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/611cc9d1-839e-40f0-8a39-df6ef586ab8d">

Pour un groupe 2 avec 300 personnes:
<img width="151" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/60b93970-8321-4f67-9c0e-57553d54fcf2">

Donc un groupe très bien organisé ne peut rien faire face a un groupe 3 fois plus nombreux.
# Extention possibles:

Les groupes pourraient faire de vrais dessins, avoir différentes couleurs.

On pourrait avoir un nombre de personnes par groupe qui varie aussi. La nuit par exemple il y a moins de personnes.

Automatiser le processus pour trouver la valeur optimale d'une variable quand toutes les autres sont fixées.

Les groupes pourraient avoir des stratégies sur quel pixels placer en premier.


