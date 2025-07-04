# another-pen-plotter

## Objectif

Creer un pen plotter rapide et precis avec un magasin fixz pour changement outils/couleur automatique avec des pieces de recup d'imprimante 3D

Après recherches il faut respecter plusieurs contraintes 

## Precision et repetabilité:
- Structure solide avec plateforme travail parallele avec les axes
- amortissement des vibrations 
- double fdc un optique et un mecanique NF sur x et y
- routine de homming (optique) avabt et après chaque changement d'outils
- systeme de centrage mine pour multicouleurs ?
- mircro stepping 32 ou 64 pas
- parametres outils adapté (vitesse max, acceleration min/max, force max, force min, etc )
- Detection presence outils sur chariot X

  
## Securité :
- Systeme de capots et reduction vitesse si capot ouvert
- Arret d'urgence
- Alimentation externe + Fusibles 12V (voiture) adapté
- 
  



## Structure mécanique

- Utilisation de profilés aluminium 2020 comme support de base.
- Glissières de récupération :
  - 2x D10 x 340 mm
  - 2x D8 x 410 mm
- 2 moteurs pas à pas NEMA17 de récupération.
- Recyclage d'une carte d'imprimante 3D (avec fins de course, smart controller, carte SD).
- Recyclage de courroie GT2 6 mm.

  
### Chariot X/Y

- Cinématique en H-Bot 
- Solénoïde pour l'abaissement de l'outil :
  - Course : 3 à 7 mm
  - Temps de réponse : < 100 ms
  - Force : 0.5 N à 2 N
  - Contrôlé par PWM via MOSFET
- Servomoteur pour prise et maintien du manchon (support stylo) :
  - Maintien stable sans mouvement parasite.
  - Repositionnement répétable dans le magasin.
  - Capteur de présence du manchon sur le chariot pour vérification avant déplacement ou impression.

### Magasin couleur / outils

- Magasin fixe, positionné à hauteur du chariot (solénoïde désactivé).
- Rangement des stylos de manière compacte et répétable.
- Intégration d'aimants pour faciliter le repositionnement du manchon dans son logement.
- Éviter tout risque de détachement ou d'erreur de positionnement lors de la pose ou prise => utiliser un "clip" pour bloquer le manchon sur le magasin 

## ameliorations possible 

- support metalique aimanté pour tenir la feuille avec aimants
- Incliner legererment le stylot (2 a 5°) => réduit les à-coups à l’impact.
- Montage souple du solénoïde => Monté sur silent-blocs ou mousse fine = moins de vibration → meilleure précision.
- Ajout d'un petit pad d’essuyage de pointe => evite les bavures 
- Coulisse Z par glissière linéaire ou tige D3 => Permet au stylo de descendre bien droit sans jeu latéral → traçage net.
- Pieds hauteur reglable + Niveau à bulle intégré pour mettre le plotter de niveau
- Affichage OLED ou TFT pour controle et suivit
- Autotest au démarrage : présence manchons, test solénoïde, test servo.
- Support scalpel / cutter pour découpe vinyle.
- Embossage (outil en pointe pour pression sur alu ou papier épais).
- Mode démo automatique : enchaînement de tracés pour tests.
- Éclairage LED RGB : visualiser les états (stylo actif, pause, erreur).
- Caméra time-lapse intégrée.
- ajout moteur axe derouleur papier 

## 🧩 STRUCTURE GÉNÉRALE
- Bloc X/Y : mouvement H-Bot
- Bloc Chariot : pince, solénoïde, capteur de présence
- Bloc Magasin : support fixe de stylos/outils
- Bloc Alimentation : transfo, ventilation, MOSFET
- Bloc Contrôle : carte mère, drivers, écran, SD

### 🧱 ASTUCES DE CONSTRUCTION

#### ⚙️ Base & structure

- Base rigide en MDF ou alu composite, stable et facile à percer.
- Pieds réglables pour s’adapter aux irrégularités du support.
- Capot avant pivotant ou amovible pour accès facile à la zone de travail.
- Zone de rangement intégrée (tiroir ou compartiment) pour accessoires.

#### 🧰 Fixations et câblage

- Connexion d’alimentation rapide et sécurisée (XT30/XT60 ou Wago).
- Passage de câbles dans les rainures 2020, avec clips ou goulottes imprimées.
- Ventilation active sur bloc alimentation/électronique (mini ventilateurs).
- Potection poussière (capot transparent, brosses ou mousse sur ouvertures).

#### 🧱 Positionnement & repères

- Marques de repérage physiques (zéro mécanique) pour positionner les feuilles.
- Système de tension de courroie réglable (à vis ou à ressort).
- Bouton RESET / arrêt d’urgence en façade.

### 🖋️ OUTILS & MAGASIN
#### 🧠 Manchon normalisé

- Diamètre standard : 20 mm extérieur.
- Friction interne ou adaptateurs pour stylos de différents diamètres.
- Conception pour prise/repose répétable (gorge, cran ou encoche).

#### 📌 Magasin fixe

 - Aligné avec la hauteur du chariot à solénoïde désactivé
 - Aide magnétique (aimant néodyme au fond) pour recentrage automatique
 - Repérage des logements par couleur ou numérotation imprimée
 -  Détrompeur physique (forme, encoche, rainure) pour éviter les erreurs de placement.
 -  clip/pince pour bloquer le manchon


## TODO (prochaines étapes)

- Définir le format exact du châssis.
- Conception du chariot et du manchon universel.
- Schéma électronique avec solénoïde, servo, capteur.
- Protocole de changement d'outil (G-code ou séquence).
- Tests de force et fiabilité du maintien du manchon.
