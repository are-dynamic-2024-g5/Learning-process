## Comment poser des pixels de façon optimal.

# Qu'est ce que R/place:

R/place est un projet social où les utilisateurs de Reddit pouvaient placer un pixel de couleur sur une toile virtuelle toutes les cinq minutes. L'objectif était de collaborer avec d'autres utilisateurs pour créer des images ou des motifs sur cette toile. Cependant, étant donné que la toile était ouverte à tous et que chaque pixel était modifiable, cela a souvent conduit à des guerres de pixels où les utilisateurs s'affrontaient pour défendre ou modifier certaines parties de l'image. On pourrait citer la "guerre" entre la france et le reste du monde pendant l'édition 2022 de R/place.

-Timelapses des différrentes éditions de R/place

2017: https://www.youtube.com/watch?v=XnRCZK3KjUY

2022: https://www.youtube.com/watch?v=K5O3UgLG2Jw

2023: https://www.youtube.com/watch?v=xjOMPka5WFo

Drapeau français sur le canvas en 2022: https://www.youtube.com/watch?v=vjx61CONYww

Mais il n'y a pas que des guerres de communautés sur R/place mais également des communautés qui font de jolies chose:

Par exemple:

Une reproduction de _La Ronde de nuit_ par Rembrandt 

<img width="319" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/e6fdfcce-9d20-4d42-be19-802b47733f95">

Il y a même des animations qui sont faites:

Une reproduction du clip musical Bad Apple: https://www.youtube.com/watch?v=21wfYqPUf-s

Une reproduction de la boucle de gameplay du jeux Outer Wilds, on se reveille près d'un feu de camp, on explore, une étoile explose, retour dans le temps et on se reveille près de notre feu de camp: https://www.reddit.com/r/place/comments/15a7li0/routerwilds_animation_sound_collab_timelapse_a/

Maintenant on pourrait se dire que contre un groupe ayant 10 fois plus de membres il est impossible de gagner. Mais est ce vraiment le cas?

# Peut on gagner face à un groupe avec avantage numérique?:

Pour notre simulation, chaque groupe est caractérisé par 4 paramètres: le nombre de personnes dans le groupe, le temps entre chaque pixel moyen, un pourcentage de chance de placer un bon pixel et une couleur.

Il est évident que le nombre de personnes dans un groupe influe sur leur capacité à dessiner ou non. Le temps entre chaque pixel représente si un individu place un pixel dès qu'il peut le faire ou alors ne fais pas vraiment attention et place un pixel un peu quand il en a envie.

Sur une toile vide il est compliqué de coordonées un groupe très grand. Il est compliqué de de poser un pixel à l'endroit exact. Pour palier à ça, certaines communautées ont crées des scripts qui affiche à l'écran l'endroit exact où il faut poser un pixel. Cela permet de réduire les chances de placer un pixel au mauvais endroits.

<img width="540" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/daff7b0d-e73f-44ec-840d-9d916eb1327d">
<img width="332" alt="image" src="https://github.com/are-dynamic-2024-g5/Rplace/assets/159923584/bb18024d-fb84-447c-b1d1-b9cbb3b43c69">

Il y a beaucoup d'autre manière d'augmenter ses chances de ne pas poser de mauvais pixel comme par exemple raffraichir la page avant de poser un pixel.

On notera que les communautés osu et touhou avaient des graphes et des scripts qui s'updataient en temps réel:https://www.reddit.com/r/place/comments/156zpm4/for_the_people_accusing_bad_apple_of_using_bots/

Pour notre simulation le groupe 1 aura 50 agents, un temps moyen entre chaque pixel de 5 minutes, 90% de chances de poser un pixel correct et posera des pixels rouges. Le groupe 2 aura 500 agents, un temps moyen entre chaque pixel de 8 minutes, 50% chances de poser un bon pixel et posera des pixels verts. Donc on va faire affronter un groupe composé de 50 personnes très organisé contre un groupe dix fois plus nombreux mais moins organisé.




