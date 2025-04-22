# another-pen-plotter

## Objectif

Regrouper les choix techniques pour un pen plotter avec magasin pour changement outils/couleur automatique.

### Structure mécanique

- Utilisation de profilés aluminium 2020 comme support de base.
- Glissières de récupération :
  - 2x D10 x 340 mm
  - 2x D8 x 410 mm
- 2 moteurs pas à pas NEMA17 de récupération.
- Recyclage d'une carte d'imprimante 3D (avec fins de course, smart controller, carte SD).
- Recyclage de courroie GT2 6 mm.

  
## Chariot X/Y

- Deux options de cinématique : H-Bot ou CoreXY.
- Intégration d'un système de tension des courroies sur le chariot.
- Solénoïde pour l'abaissement de l'outil :
  - Course : 3 à 7 mm
  - Temps de réponse : < 100 ms
  - Force : 0.5 N à 2 N
  - Contrôlé par PWM via MOSFET
- Servomoteur pour prise et maintien du manchon (support stylo) :
  - Maintien stable sans mouvement parasite.
  - Repositionnement répétable dans le magasin.
  - Capteur de présence du manchon sur le chariot :
  -   Pour vérification avant déplacement ou impression.

## Magasin couleur / outils

- Magasin fixe, positionné à hauteur du chariot (solénoïde désactivé).
- Rangement des stylos de manière compacte et répétable.
- Intégration d'aimants pour faciliter le repositionnement du manchon dans son logement.
- Éviter tout risque de détachement ou d'erreur de positionnement lors de la pose ou prise.

## TODO (prochaines étapes)

- Définir le format exact du châssis.
- Conception du chariot et du manchon universel.
- Schéma électronique avec solénoïde, servo, capteur.
- Protocole de changement d'outil (G-code ou séquence).
- Tests de force et fiabilité du maintien du manchon.
