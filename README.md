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



