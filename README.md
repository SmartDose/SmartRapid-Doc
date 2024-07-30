
# Logiciel SmartRapid

Le logiciel SmartRapid a été conçu pour être relativement simple d'utilisation et fonctionner sur un écran tactile avec une conception de l'interface utilisateur épurée. Ce logiciel est essentiel pour le pilotage de la machine ensacheuse de médicaments SmartRapid T90, permettant aux utilisateurs de configurer et de surveiller les opérations de la machine de manière intuitive et efficace.

## Démarrage et Connexion

### Lancement du logiciel :
- Le logiciel SmartRapid doit être lancé après le démarrage de la machine SmartRapid T90.
- Assurez-vous que la machine est correctement connectée au PC à l'aide d'un connecteur USB A vers USB B.

### Initialisation :
- Lors du lancement du logiciel, si la connexion avec la machine est établie correctement, un son indiquera l'initialisation du plateau de la machine. Vous devriez par la suite retrouver l'interface principale du logiciel comme sur la capture d'écran ci-dessous. À ce niveau, le logiciel est prêt à recevoir de nouvelles productions par l'intermédiaire de l'API Rest ou par connexion TCP.

## Interface principale

L'interface principale du logiciel SmartRapid reste relativement simple afin de faciliter la navigation et les opérations :
![Interface principale](https://raw.githubusercontent.com/Objectif-PDA/SmartRapid-Doc/main/SmartRapid/Images/IMG_MainScreen_Annoted.png)

### Bouton principal (1) :
- Le bouton "Play" (triangle violet) au centre de l'interface permet d'accéder à la fenêtre d'assistant au remplissage du plateau de la T90. Ce bouton est grisé lorsqu'aucun ordre de production n'a été réceptionné par le logiciel SmartRapid.

### Prescriptions utilisées (2) :
- Tableau listant les prescriptions utilisées pour l'ordre de production en cours.
- Colonnes visibles :
  - **Prescription** : Nom du médicament ou de la prescription.
  - **Quantité** : Quantité totale requise pour compléter la production.
  - **Nbr. unités** : Nombre d'unités utilisées.
  - **Nbr. fractions** : Nombre de fractions utilisées.
- Exemple affiché :
  - Médicament 1 : 14 unités, 0 fractions.
  - Médicament 2 : 14 unités, 0 fractions.

### Ordre de production (3) :
- Cette section affiche la liste des ordres de production en cours.
- Colonnes visibles :
  - **ID** : Numéro d'identification du patient.
  - **Nom Patient** : Nom du patient.
- Exemple affiché :
  - ID : 1
  - Nom Patient : Patient T90

### Bouton historique (4) :
- Permet de consulter l'historique des productions effectuées.

### Bouton layout designer (5) :
- Accès au layout designer (concepteur visuel de layout des sachets).

### Bouton paramètres (6) :
- Accès aux paramètres du logiciel machine.

### Bouton SmartFelix™ (7) :
- Si un périphérique SmartFelix™ est installé dans l'environnement de l'établissement, ce bouton permet d'accéder à l'écosystème SmartAssist (SmartAssist / SmartControl).

### Affichage de la température actuelle des mâchoires de scellages de la machine T90 (8) :
- Indique la température actuelle des mâchoires de scellage, affichée en bas à droite de l'interface.
## Interface de remplissage
En cliquant sur le bouton "Play" (1) du menu principal, vous accéderez à la fenêtre visible ci-dessous :
![Interface principale](https://raw.githubusercontent.com/Objectif-PDA/SmartRapid-Doc/main/SmartRapid/Images/IMG_FillingScreen_Annoted.png)Vous retrouverez un affichage virtuel du plateau de la T90 (1) composé de 6 lignes de 15 cellules, permettant une gestion visuelle et intuitive du placement des médicaments. La disposition des médicaments sur le plateau peut être configurée selon vos préférences et besoins spécifiques. Plusieurs options de remplissage sont disponibles (configurable dans la fenêtre de paramétrage) :

-   **De gauche à droite, de bas en haut** : Les cellules sont remplies en commençant par le coin inférieur gauche et en remontant ligne par ligne.
-   **De droite à gauche, de bas en haut** : Les cellules sont remplies en commençant par le coin inférieur droit et en remontant ligne par ligne.
-   **De gauche à droite, de haut en bas** : Les cellules sont remplies en commençant par le coin supérieur gauche et en descendant ligne par ligne.
-   **De droite à gauche, de haut en bas** : Les cellules sont remplies en commençant par le coin supérieur droit et en descendant ligne par ligne.

Vous retrouverez vos patients à produire dans le tableau en haut à gauche (2). Sélectionner un patient viendra charger ses médicaments à remplir dans le tableau en bas à gauche (3). Lorsqu'il s'agit d'une spécialité en Externe, le texte du médicament sera affiché en rouge dans le tableau et en vert pour les médicament en Si Besoin.
 Le plateau virtuel de remplissage se mettra à jour en conséquence :
- Les cellules avec le statut à remplir pour le médicament sélectionné (3) se colorerons en Orange avec la quantité à placer pour chaque cellule indiqué à l'intérieur de ces dernières.

Après remplissage physique du plateau, il suffit d'appuyer sur le bouton "Remplir" (4) pour accéder à la fenêtre de scan de la boîte (ci-dessous).

![Interface principale](https://github.com/Objectif-PDA/SmartRapid-Doc/blob/main/SmartRapid/Images/IMG_ScanScreen.png?raw=true)
Après saisie des informations de traçabilité et validation, la ligne du médicament dans le tableau (3) passera en vert. De même sur le plateau virtuel, lors de la re-sélection du médicament dans le tableau, les cellules affricherons désormais en vert, indiquant que la spécialité courante à bien été remplie.

![Interface principale](https://raw.githubusercontent.com/Objectif-PDA/SmartRapid-Doc/main/SmartRapid/Images/IMG_FillingScreen_FilledPill.png)![Interface principale](https://raw.githubusercontent.com/Objectif-PDA/SmartRapid-Doc/main/SmartRapid/Images/IMG_FillingScreen_FilledPill2.png)
Lorsque le remplissage de tout les médicaments à correctement été effectué, le bouton "Remplir" (4) changera d'aspect, présentant un icône "Play" indiquant que la production est prête à être envoyée à la machine.
Une barre de production avec l'état de la machine devrait apparaître en bas de la fenêtre (5) permettant de suivre en temps réel la production courante.
![Interface principale](https://raw.githubusercontent.com/Objectif-PDA/SmartRapid-Doc/main/SmartRapid/Images/IMGF_ProductionSequence.gif)
Il est possible de sélectionner et renvoyer uniquement certains sachets spécifiques d'une production en cours de remplissage en cliquant sur le bouton "Renvoyer des sachets spécifiques" (7) en haut à gauche.

Cette action ouvrira la fenêtre visible ci-dessous, qui vous permettra de filtrer les sachets disponibles par jour et par heure de prise. Pour sélectionner les sachets à reproduire, cliquez simplement dessus, puis cliquez sur le bouton "Charger la sélection" pour fermer la fenêtre et revenir à l'écran de remplissage. Les cases à remplir / s'afficheront cette fois en violet.

![Interface principale](https://raw.githubusercontent.com/Objectif-PDA/SmartRapid-Doc/main/SmartRapid/Images/IMG_FilterPouchesScreen.png)![Interface principale](https://raw.githubusercontent.com/Objectif-PDA/SmartRapid-Doc/main/SmartRapid/Images/IMG_FillingCustomPouchesScreen.png)
