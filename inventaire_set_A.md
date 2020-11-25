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
  
### Le wagon trémie

### Le wagon tombereau

### Le wagon citerne

### Le rail d'alimentation

### Les rails droits

### Les rails courbes
  
### Elements de maintien des rails
