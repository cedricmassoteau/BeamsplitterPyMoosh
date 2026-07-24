Lors de ce stage, on devait obtenir des formes géométrique en changeant simplement l'épaisseur et l'indice otpique des couches d'une structure multicouche.

L'une des formes les plus simple à former avec une gaussiène est le triangle.


<img width="640" height="480" alt="Image" src="https://github.com/user-attachments/assets/76bb7145-ad2b-4417-a6ea-b347e660febc" />
https://github.com/cedricmassoteau/BeamsplitterPyMoosh/blob/22922d62447a7f50260c3b8b4d987364fcba99c8/Triangle

Après cela, je me suis dit qu'une tête de chat, qui n'est au final que 2 triangle et une ligne droite fonctionnerait bien.

<img width="800" height="400" alt="Image" src="https://github.com/user-attachments/assets/a030649a-1df7-4539-a79b-82a1647ac75c" />
https://github.com/cedricmassoteau/BeamsplitterPyMoosh/blob/22922d62447a7f50260c3b8b4d987364fcba99c8/catsears

Enfin il étais temps d'essayer de reproduire des phénomène physique, en l'occurence le beam splitter, il étais compliqué de se restreindre à des profils géométrique à ce moment là.En effet l'écartement idéal et la position des 2 "gaussiène" est assez dépendant du waist, du nombre de couches.En l'enfermant dans une forme précise, il aurait été compliqué de trouver un résultat acceptable.
A la place, j'ai utilisé une librairie scipy appeler find_peaks afin de localiser les pics et la fonction était pénaliser si il y avait moins de 2 pics et si le premier pics avait une intensité trop basse.Ensuite il pénalise si l'intensité se trouve ailleurs que dans les pics,si les pics ne sont pas identique en largeur et si ils sont trop proches.

De plus, si on va dans profil_R_2 et qu'on choisit de mettre NSfield en True, alors on sera en réflection sur la première épaisseur, si il est en False, nous sommmes en transmission sur la dernière épaisseur.

Par ailleurs, le code n'est pas finis, les 2 pics obtenus ne sont pas toutes 2 des gaussiène, ainsi j'ai tenté de mélanger les 2 méthode.Soit la méthode "pics" décrit juste avant et la méthode "cible" décrit avec le triangle et la chat. Cette dernière méthode,appelé "hybride" est utilisé pour la dernière image .

Entre le début du codage et le code actuel, il y a des différence d'affichage, le code actuel affiche en haut la composition de la structure,puis le profil et enfin l'évolution du coût . De même, tous les profils et pas seulement le meilleur est affichée.

Pour se diriger, le meilleur moyen est d'utiliser ctrl + f et de chercher des mot clés tel que k_val(pour bornes des indices et épaisseurs), n_run(pour nbre de run et au_dessus,il y a les épaisseurs des runs, ex k_value=[25,30] et n_run = 2, alors 2 run se feront à 25 couches puis à 30 couches.), methode_cout(choisit entre "cible","correlation" et "pics") et forme_cible(choisit la forme),aligner_affichage_sur_premier_pic(change l'affichage pour que le pic 1 soit toujours à gauche mais ne change pas l'optimisation elle-même),budget,patience,tol(actuellement il faut que le programme ait une amélioration d'au moins 0.01 en 800 itérations)

https://github.com/cedricmassoteau/BeamsplitterPyMoosh/blob/7c3fd31f722465dd6d54254c9ca69bdeaa5f0bee/beamsplitter

<img width="1370" height="715" alt="Image" src="https://github.com/user-attachments/assets/01979982-26d6-4efc-82bd-3431307e6f2b" />

<img width="1370" height="715" alt="Image" src="https://github.com/user-attachments/assets/79dafe88-7bf0-4593-987b-2b33da0ecdcd" />

<img width="1370" height="715" alt="Image" src="https://github.com/user-attachments/assets/e7473498-cfc0-4302-a397-6d9ce0bbc2b4" />
<img width="1370" height="715" alt="Image" src="https://github.com/user-attachments/assets/e72d3213-cc05-4aaa-9e45-4d839ae9808e" />

On voit que cela fonctionne correctement pour un nombre de couches aussi bas que 5 couches, à noter que plus il y a de couches, plus les chances de trouver une structure adéquate est grande.

<img width="1366" height="711" alt="Image" src="https://github.com/user-attachments/assets/8544959e-40a0-4ed0-adec-2c3deec38f97" />

On peux tester autant de run que l'on veux, ici il y en a 60 par exemple à 5 couches.

<img width="400" height="715" alt="Image" src="https://github.com/user-attachments/assets/eddabd74-e321-46fe-9f0a-94d567c7a9ca" />

Avec un budget de 500k et 5 couches, on obtient ce résultat là. Sait-on jamais que ce soit utile.

<img width="1366" height="711" alt="Image" src="https://github.com/user-attachments/assets/5523423f-85c9-4873-83ba-ba7d53064edd" />

Enfin lorsque vous ferez tourner le programme, vous devriez obtenir ceci, actuellement en méthode "hybride". Ce que je voulais faire, mais j'ai pas réussis, c'est d'utiliser la tête de chat plus haut avec la méthode hybride.
