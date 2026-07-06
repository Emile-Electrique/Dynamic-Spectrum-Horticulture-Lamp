<img width="2339" height="1653" alt="system-bloc-photon-drive-1" src="https://github.com/user-attachments/assets/eb85de5a-d365-426f-8ae6-19bb1c070585" />


# Description du projet

## Objectif général

Le projet consiste à développer un système d’éclairage horticole intelligent capable d’ajuster sa puissance et son spectre lumineux de manière précise, mesurable et automatisée. Contrairement à un éclairage horticole conventionnel qui applique une puissance fixe ou une simple gradation globale, cette plateforme vise un contrôle indépendant de chaque canal lumineux afin de mieux répondre aux besoins spécifiques des plantes et aux conditions réelles de l’environnement.

Le système est conçu comme une plateforme expérimentale de recherche et développement. Il servira à tester différentes recettes lumineuses, à observer leur impact sur la croissance des plantes et à comparer les résultats avec des solutions d’éclairage plus simples ou de commodité.

## Vision du système

La vision du projet est de créer un éclairage qui ne fonctionne pas uniquement en mode ouvert, mais qui observe son environnement et ajuste son comportement en conséquence. En intégrant des capteurs d’intensité lumineuse et des capteurs spectraux, le système peut mesurer la lumière disponible, estimer la contribution de la lumière naturelle et adapter la puissance des LED pour maintenir une cible lumineuse plus stable.

Cette approche permet d’explorer une stratégie d’éclairage en synergie avec la lumière ambiante. Par exemple, si la lumière naturelle augmente durant la journée, le système peut réduire sa contribution artificielle. À l’inverse, lors d’une baisse d’ensoleillement, il peut compenser automatiquement afin de maintenir une quantité de lumière plus constante pour les plantes.

## Modularité matérielle

Le système est conçu autour de tuiles lumineuses de 50 W. Une installation peut utiliser deux, trois ou quatre tuiles, pour une puissance totale typique de 100 W à 200 W. Cette modularité permet d’adapter la plateforme à plusieurs contextes :

* petits bancs d’essai expérimentaux ;
* culture intérieure à échelle réduite ;
* essais comparatifs entre recettes lumineuses ;
* prototypes destinés à une éventuelle application commerciale ;
* systèmes de démonstration pour l’agriculture contrôlée.

Chaque tuile peut être associée à son propre dissipateur thermique, ce qui facilite l’assemblage, la maintenance et l’évolution du système. Cette approche modulaire évite de concevoir une seule lampe monolithique difficile à modifier.

## Contrôle précis des canaux lumineux

Un des points centraux du projet est le contrôle précis et indépendant de chaque canal lumineux. Chaque canal peut être piloté individuellement afin d’ajuster la contribution de différentes bandes du spectre. Cette architecture permet d’expérimenter avec plusieurs ratios lumineux et de documenter leurs effets sur les cultures.

Le contrôle indépendant des canaux permet notamment :

* d’ajuster l’intensité globale sans perdre le contrôle du spectre ;
* de modifier le ratio entre les différentes longueurs d’onde ;
* de tester différentes recettes lumineuses selon le stade de croissance ;
* de compenser les variations de lumière ambiante ;
* de comparer des stratégies d’éclairage fixes et dynamiques.

Cette précision est importante, car la valeur du système ne vient pas seulement de sa puissance électrique, mais de sa capacité à appliquer la bonne lumière, au bon moment, avec un niveau de contrôle reproductible.

## Gestion thermique

Les tuiles lumineuses sont conçues autour d’un substrat en aluminium afin d’améliorer le transfert thermique entre les LED et le dissipateur. L’objectif est d’extraire efficacement la chaleur générée par les composants lumineux et de la diriger vers une masse thermique adaptée, plutôt que de laisser cette chaleur s’accumuler près des LED ou se diffuser directement vers les plantes.

Le système ne prétend pas éliminer la chaleur, puisque toute puissance électrique finit éventuellement par être dissipée sous forme thermique. L’objectif est plutôt de contrôler où cette chaleur est dirigée, comment elle est évacuée et comment elle influence l’environnement de culture. Cette distinction est importante dans une démarche d’ingénierie réaliste.

Une bonne gestion thermique permet aussi d’améliorer la stabilité lumineuse, la durée de vie des LED et la répétabilité des essais expérimentaux.

## Capteurs et boucle fermée

La plateforme prévoit l’intégration de plusieurs types de capteurs afin de mesurer l’environnement lumineux réel. Ces capteurs peuvent inclure des mesures d’intensité globale, de lumière visible, de rayonnement utile aux plantes ou de bandes spectrales spécifiques.

Ces données permettent au système de fonctionner en boucle fermée. Au lieu d’appliquer une consigne fixe sans rétroaction, le contrôleur peut comparer la lumière mesurée à une cible et ajuster les canaux lumineux en conséquence.

Cette approche ouvre la porte à plusieurs modes de fonctionnement :

* maintien d’une intensité lumineuse cible ;
* compensation de la lumière naturelle ;
* suivi d’une recette lumineuse sur 24 heures ;
* ajustement progressif selon le stade de croissance ;
* comparaison entre contrôle manuel, contrôle programmé et contrôle automatique.

## Positionnement expérimental

Le système est actuellement positionné comme une plateforme expérimentale. Il ne s’agit pas encore d’un produit finalisé, mais d’un outil de développement permettant de valider des choix techniques et agronomiques.

Les performances du système seront comparées à celles d’éclairages de commodité afin de documenter clairement ce que la plateforme apporte en plus : précision, stabilité, efficacité énergétique, contrôle spectral, modularité et potentiel d’automatisation.

Cette démarche comparative est essentielle pour éviter de développer une technologie impressionnante sur papier, mais difficile à justifier en pratique. Le projet devra démontrer sa valeur par des mesures, des essais et des résultats documentés.
