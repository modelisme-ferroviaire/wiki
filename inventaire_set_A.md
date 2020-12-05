# Inventaire et état des éléments du set A

## Composition 

  - 1 transfo 
  - 1 locomotive vapeur
  - 1 wagon trémie
  - 1 wagon tombereau
  - 1 wagon citerne
  - 1 cable permettant d'alimenter la voie
  - 2 rails droits 
  - 11 rails courbes
  - 1 rail courbe avec prise d'alimentation
  - des petits éléments en plastique permettant de garder les rails solidaires les uns des autres
  - un livret explicatif sur les boites d'extension, et comment exploiter ses trains à partir de ces boites.
  
## Détails des éléments

### Le transfo

#### Description 

Le transfo fournissait a partir du 220 V, une tension alternative de 15V (d'après la plaque aiu dessous, mais l'affichage au dessus indique 14v) pour la commande des aiguillages et autres éléménts de voie, ainsi qu'une tension continue  variable de 0 à 14v (la plaque signalétique parlerait plutôt de 11,5v, à vérifier au multimètre) pour commander la locomotive. Il était censé être protégé contre les courts circuits.

La tension alternative est repérée par deux plots de connection noirs, tandis que l'alimentation continue était fournie par deux plots colorés l'un en jaune et l'autre en bleu.

Chaque voie (continue ou alternative) est limitée à 1 ampère. La limite de puissance pour les deux voies (continue et alternative) est de 10W.

Un rheostat permettait de régler le sens de circulation ainsi que la vitesse du train.

Note : Pour avoir connu le même type de matériel fourni par Jouef, je peux dire que le matériel Roco à l'époque était de bien meilleure qualité.

J'ai regardé comment l'ouvrir, pour vérifier la protection contre les courts-circuits mais je n'y suis pas encore parvenu (je risque d'endommager le boitier, et je n'y tiens pas). Il faudra dnc que je trouve un autre moyen  de tester ce point.

#### Tests

Avant de brancher une locomotive ou du matériel de voie sur ce transformateur, je vais m'assurer qu'il est toujours en état de marche, et que les tensions fournies sont toujours bien celles spécifiées sur la plaque. Je ferai une mesure à vide, une mesure avec charges diverses pour voir le comportement, et enfin j'utiliserai une locomotive "de test" ou un moteur pour m'assurer que tout fonctionne comme prévu. 

##### Alimentation alternative

Tension 
a vide :
Charge 10 K
Charge 5k
Charge 1k (courant ...)

Charge 1A (Résistance xxx, YYY W)

Forme d'onde a l'oscilloscope

Il s'agit d'une tension alternative de x volts crête à crête (à vide), impossible de contrôler. Cette tension doit probablement être issue du secondaire du transfo,n avec probablement une protection contre les surintensités quelque part.

[ TODO ] Mettre une image

##### Alimentation continue


Tension a vide :
Charge 10 K
Charge 5k
Charge 1k

Charge 1A (Résistance xxx, YYY W)

Forme d'onde à l'oscilloscope.
Tension de xx V redréssée (double alternance), mais non filtrée. Bon à savoir.

Valeur RMS:
Valeur Crête: 
[ TODO ] Mettre une image

Utilisation d'un moteur

Forme d'onde à l'oscilloscope.


#### Résultat

L'alimentation fournit des valeurs de tension plus élevée qu'indiqué. Certains prétendent que le problème pourrait venir du fait qu'à l'époque, la tension du sectreur était de 220V, mais que depuis elle a été ramenée a 230V. Cette explication ne me convainc pas trop, dans la mesure ou, si on calcule rapidement le rapport de multiplication, on ne voit pas de telle différence. De plus j'ai effectué une mesure de la tension d'alimentation secteur au multimètre, et j'ai bien 220V. Le problème doit venir d'ailleurs (probablement du type de tension dont on parle : tension efficace, crête à crete, etc .... j'ai un boulot de recherche à faire !!!).

Note : d'après https://sonelec-musique.com/electronique_theorie_transfo.html, une mine d'or pour qui veut des infos sur l'électronique, "le secondaire d'un transformateur d'alimentation peut délivrer une tension supérieure à celle annoncée. En règle générale, la tension spécifiée (vendue) est celle obtenue quand on demande son maximum au transformateur, c'est à dire que **son courant secondaire correspond à la valeur max pour laquelle il est vendu**. Cela implique la plupart du temps une tension plus élevée quand on demande moins que le courant max. **La tension maximale est obtenue à vide**, c'est à dire quand le secondaire n'est relié à rien, et **peut atteindre une valeur de 10% à 30% supérieure à la valeur nominale**. La différence entre tension en charge (secondaire branché à un circuit qui consomme du courant) et tension à vide (secondaire non raccordé) est **d'autant plus importante que la puissance du transformateur est faible.** 

Ce point a été abordé au lycée quand j'étais en première ou terminale (d'ou mon intéret de comparer la tension à vide), mais je ne m'en rappelais plus exactement le pourquoi du comment (ce n'est pas pour rien que plus haut j'ai mentionné les mesures de tension à vide : il y avait un souvenir encore dans ma tête mais pas net au point de me rappeler exactement le pourquoi du comment).



#### Comparaison avec une autre alimentatio plus moderne

##### Modèle

Il s'agit d'une aliemntation fournie avec le coffret Thalys MEHANO (que l'on trouve souvent aux périodes de fêtes pour moins de 100 euros). 
L'alimentation est composée en deux blocs :
  - un bloc de transformation 220 => 16v alternatif 500 mA 8 vA
  - un bloc régulateur/vbariateur permettant de fournir une tension continue variable de 0 à 13v, 400mA 5,2w (modè-le F370)
  
La mesure au multimètre indique que le secondaire du transfo fournit une tension de 18,5v
La mesure a l'oscilloscope montre une tension secondaire non filtré a 17,5V (approximativement, l'oscilloscope n'étant pas en mesure d'afficher clairement le signal, qui a l'air de dépasser légèrement ses caractéristiques d'entrée), alternative à 50 Hz.
 
La tension a vide mesurée sur le secondaire est de +21,2v ou -21,2v en fonction du sens de circulation (élevé par rapport aux 13V annoncés !!!). La mesure à l'oscilloscope montre une tension redressée et filtrée, contrairement à l'ancienne alim qui ne se contentait que de redresser le courant.

En y branchant un moteur (motoréducteur) comme charge, la tension redescend à plus ou moins 18,4V selon le sens de rotation (ça reste beaucoup !!!). Elle reste relativement stable lorsqu'on l'observe à l'oscilloscope (on voit quand même certains parasites à haute fréquence, mais un condensateur bien choisi devrait régler ces problèmes - ça fera l'objet d'un autre article).

Je vais tenter de trouver une charge de type résistive pour tester un peu plus en profondeur ...


#### Y a-t-il des risques à utiliser ce transfo ?

A première vue, je dirais que pour le matériel un peu ancien (mon ancien train, ou d'autres anciens trains Jouef), le risque est plutôt limité : ce matériel n'est équipé que d'un moteur et éventuellement d'une lampe (la tension élevée est peut-être la raison qui fait que la lampe de mon premier train a vite grillé ?). De plus il y a un calcul et une mesure que je n'ai pas réellement faite, c'est celui de la tension efficace (ou RMS - a vérifier) qui peut être plus basse et plus conforme à la signalisation de la plaque de transf (recherches à faire). Par contre pour le matériel un peu plus récent, je suis plus septique : j'ai vu que de nos jours, certaines locomotives sont équipées d'une circuiterie electronique (mais qu n'est paut-être utile que lorsqu'on leur insert un décodeur digital ?). Quoi qu'il en soit je pense que tant que je n'aurai pas vérifié un certain nombre de points, je n'utiliserai pas ces alimentation au maximum de leur capacité. Je pense même leur ajouter un circuit de mesure de la tension de sortie (articlez à venir), et j'éviterai d'utiliser la loco roco sans avoir vériié s'il y a un risque pour le matériel récent à l'utiliser.



### La locomotive vapeur


#### Présentation
La locomotive en question est une locomotive de gamme "junior" - ce qui signifie qu'elle est moins détaillée, donc moins fragile qu'une locomotive de gamme au dessus. Cependant, force est de constater que la qualité était là : bon niveau de détails, bonne tenue sur les rails, etc ...  ( TODO: Essayer de trouver la référence). Elle avait en avant une lampe, qui malhereusement n'a pas duré très longtemps.

#### Etat de la locomotive
Aujourd'hui elle est démontée (photo à montrer) : je suis en train de la nettoyer et de la graisser. De mémoire elle a deux problèmes : un problème de lampe, et un problème de pignon d'entrainement du moteur. Comme ça fait longtemps que je ne l'ai plus faite fonctionner je ne sais plus trop à ce niveau ce qui n'allait pas. Donc dans un premier temps je vais la remonter, et l'essayer sur un circuit de rails. De plus une des échelles latérales de la caisse est cassée : j'ai les morceaux mais je ne sais pas trop comment la recoller de façon à ce qu'elle tienne bien. Enfin, les attaches des wagons ont des petits soucis : des morceaux de plastique permettant de les maintenir en place sont cassés, et je devrai soit les remplacer, soit trouver un moyen de compenser ce manque.

#### Reste à faire pour restaurer

  - Nettoyage des pignons
  - nettoyage des roues
  - nettoyage moteur
  - changer lampe
  - regraisser pignons
  - graisser axe roues
  - remonter moteur
  - remonter pignon
  - remonter roues
  - tester ensemble moteur+roues (vérifier entrainement)
  - corriger problème de transmission s'il existe encore
  - recoller échelle sur caisse
  - remonter caisse
 
### Les wagons 

#### Le wagon trémie

Le wagon trémie n'a pas forcément bien vieilli non plus. Il était composé d'un chassis et d'une trémie rouge amovible. Cette trémie pouvait basculer. J'ai retrouvé le chassis, mais pas la trémie. Les essieux sont en bon état, mais e dessus du chassis est un peu courbé. Il y a probablement une plaque de métal à l'intérieur pour le lester  (j'en déduis ça au poids de l'objet). Peut-être la plaque a-t-elle plié ? Il n'y a qu'une seule marche d'un côté. l'autre côté est probablement cassée, mais la trace est difficile à voir. Comme j'ai retroué un wagon équivalent sur ebay, he ferai ue comparaison des deux élémants pour voir si ça manque réellement. Si le manque de marche ne gène pas l'apparence des wagons, je ne la remplacerai pas. JE risque d'empirer l'état général plutôt que de l'améliorer. Il y a aussi un tampon qui est cassé ...

liste des problèmes constatés :

  - manque la trémie
  - chassis bombé
  - manque aparamment une marche
  - vérifier l'état de la plaque à l'intérieur.
  
#### Le wagon tombereau

Le wagon tombereau est peut être le wagon qui est resté dans le meilleur état. Il a néamoins perdu le système permettant de fixer 'attache au wagon, et je l'ai remplacé à l'époque par une vis que j'avais sous la main ... Ca tient, mais la vis ressort beaucoup sur le dessous du wagon. Elle risque d'entrer en contact avec certains éléments tels que les éléménts permettant de détacher les wagons dans les sets D et E.

Il y a quelques marques de casse et un eu de poussière, et par le dessous on peut constater qu'il y a une plaque de métal ( qui s'est un peu oxydée) dans le wagon. Cette plaque permet de lester ce dernier de façon à éviter les déraillages.  L'état général du wagon est plutôt bon : le wagon peut rouler, et j'essaierai de trouver un moyen de réparer ou de cacher la casse. J'essaierai également de sortir la plaque pour enlever la rouyille dessus, et éventuellement lui appliquer une peinture anti rouille. Il a juste besoin d'un petit nettoyage.

Les essieux ont, eux non plus, pas trop souffert. On voit qu'iols ne sont pas neufs mais ça ne pose pas problème. Je passerai un peu de temps à le déonter, nettoyer les parties plastiques et désoxyder la plaque à l'intérieur. Afin d'avoir un modèle de wagon en bon état, je m'en suis procuré un identique (enfin presque) sur ebay. Ca me donnera peut-être des idées pour restaurer les parties déteriorées.

Liste des problèmes constatés :

  - Attaches fixée avec une vis qui dépasse au lieu d'un morceau de plastique (nom à trouver).
  - l'attache fixée par la vis a perdu la pointe permettant de s'attacher à un autre wagon
  - plaque à l'intérieur oxydée
  - marche sur cassée
  - partie marron aux extrémités cassée d'un côté, fragilisée de l'autre
  - tampon cassé
  - poussière a l'intérieur.


#### Le wagon citerne

Je n'arrive plus à mettre la main dessus .... Le seul élément que j'ai trouvé est l'espèce de passerelle ou balcon permettant d'accéder à l'ouverture du haut du wagon, et cet élément est en piteux état. En attendant de le retrouvr, j'ai acheté un remplaçant identique sur ebay. Mais il est possible que je ne le retrouve jamais: à un moment je suis tombé dessus et me suis demandé si j'allais le garder ou non. Peut être que je m'en suis débarassé. Au pire si je le retrouve, je ferai une mise à jour ici.

### Les rails 

Liste des problèmes constatés :

  - Oxydation
  - éclisses
  - traverses
  - traces noires sur le dessus
  - rayures en dessous
  
#### Le rail d'alimentation

Le rail d'alimentation est un rail courbe (ref Roco 4562). Le rayon et l'angle de ce rail sont identiques à ceux des 5 autres rails courbes du coffret, la seule différence avec ceux-ci etant la présence de bornes d'alimentation. 

Les fils d'limentation se connectent sur les bornes via des vis. ( vu la couleur, les bornes et les vis sont probablement en laiton). La connection aux rails se fait en dessous de deux traverses (voir photo). Bornes et vis ont un peu noirci, il faudra que je les nettoie un peu, comme les rails en eux même qui laissent apparaître quelques traces (les traces habituelles que l'(non trouve sur les rails qui ont été utilisés). Il y a aussi quelques rayures sur les traverses par le dessous. Je pense que je devrai également changer les éclisses. Cela dit pour un rail d'au moins 25 ans, il est en très bon état (bien meilleur que des rails Jouef ou Mehano pluis récents).

Liste des problèmes constatés :

  - comme les rails en général
  - vis et cosses de prise de courant noircies
  - Oxydation et rayures sur les lamelles d'alimentation
  - cosses à changer
  
#### Les rails droits

Contrairement aux rails courbes, il m'est impossible d'identifier les rails droits d'origine du set A. Dans le set, il y avait deux rails référencés Roco 4402. PAs d'indicvation sur leur longueur mais il est facile de les mesurer : 22,9 cm de longueur. La largeur des traverses est de 2,95 cm. On trouv ces rails dans quasiment tous les coffrets complémentaires (seul le coffret D n'en a pas). Je prendrai donc deux rails au hasard et considèrerai que ces rails font partie du set A.

Liste des problèmes constatés :

  - comme les rails en général
  
#### Les rails courbes

Les rails courbes sont facilement identifiables car seul  le set A fournit les rails de ce rayon et de cet angle : rayon 358 mm, angle 30°). Il faut 6 rails de ce rayon pour faire un cercle. Le rayon est assez petit. J'ai essayé une fois de faire passer un Thalys Mehano dessus, mais la longueur des wagons TGV fait que ce n'est pas très beau (je ne sais pas si 2 tgv pourraient se croiser). Mais comme à l'origine le set accueille une locomotive et des wagons de petite taille, ce n'est pas grave. Je sais juste que je ne pourrai pas y faire passer de TGV !!! :).

L'état de ces rails est semblable à celui des autres : un peu de noircissement et légère oxydation, quelques rayures sur le dessous et probablement des morceaux extérieur de traverses qui ont du tomber (j'ai quelques rails comme ça).

Comme pour les autres rails, un nettoyage et un dégraissage, et probablement un changement d'éclisses sera nécessaire.

Liste des problèmes constatés :

  - comme les rails en général

## Elements de maintien des rails

Le set A était composé également de petits éléments plastique permettant de garder les rails maintenu ensemble. Seul le coffret A disposait de ces éléments. Les autress set ne les fournissaient plus. Probablement parce que l'ensemble est destiné à être fixé sur un élément stable. Ces éléments rendaient deux rails solidaires l'un de l'autre en se fixant sur les traverses situées juste à la jointure des rails. Il ne m'en reste qu'une seule.

# Tableau récapitulatif des éléments à vérifier/changer
| Element |
|--
| Alimentation | 
| Locomotive |
| Wagon tombereau |
| Wagon trémie |
| Wagon citerne |
| Rails droits |
| Rails courbes |
| Rails d'alimentation |
| cable d'alimentation des rails |
| Elements de maintien des rails |

Nécessaire à commander :


    - éclisses : 12 rails courbes + 2 droits, soit 14 rails. En considérant qu'il faut deux éclisses par rail, il en faut au minimum 28 dans le cas ou je devrais tout remplacer.
    - toile émeri ou chiffon ?
    - essence C pour dégraisser
    - Locomotive : 
      * huile
      * graisse pour les pignons
      * attaches pour les wagons
    - wagons :
      * attaches de remplacement
    - fils d'alimentation:
      - fil jaune et bleu
      - connecteur entre fils
      
Par quoi commencer ?
- Loco
  1. Terminer le nettoyage (dégraisser, désoxyder les contacts, ...)
  2. Remettre de l'huile
  3. Remonter les éléments
  4. Graisser les pignons
  5. Huiler les essieux
  6. Changer les attelages
  7. Réparer les marches
  8. Changer la lampe
      
- Rails
  1. Nettoyer
  2. désoxyder
  3. Remplacer les éclisses
    
