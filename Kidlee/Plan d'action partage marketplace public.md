# Besoin
1. pouvoir partager les missions sur les réseaux sociaux(**RS**)
2. pouvoir partager les missions via message (lien et apercu sur les app de chat ex. messenger, whatApp)

# Partage RS via bouton
il existe de splatformes qui propose des plugins de partage sur differents réseaux sociaux exemple [ShereThis](sharethis.com) configurable en terme d'affichage principallement et qu'en suite on peut facielement integrer sur les pages souhaité via un tag javascript simple.
## Process d'integration
1. un header doit etre rajouté sur les pages qui sont concernés par le domaine configuré sur **ShareThis** pour prouver que le domain appartient bien a Kidlee.
2. configurer les bouton sur la platforme
3. insérer le code Javascript fournit par la platforme

**NB**: Vue que les boutons de partage se résume finallement a un partage de lien il faut du coups apporter les améliorations sur les méta tags qui serons propsé dans la section suivante.

# Partage sur les app de chat:
Quand on partage sur les app de messagerie un crawler va venir parcourir le lien et extraire des info de cette page pour préparer un aperçu.
pour tester les aperçu on peut utiliser cet outils gratuite: [SocialSharepreview](https://socialsharepreview.com/?url=https://app.kidlee.fr/marketplace/4619) 
Les méta tags a rajouté sont: 
* Balise `og:title` pour donner un titre a la page. un titre doit suivre les recommendations suivantes:
	* ne pas dépasser les 60 caractères.
	* Avoir le sujet de la page en premiere partie du titre
* Balise `og:description` qui permet de fournir une description de la page (ici de la mission): recommendations:
	* entre 55 et 200 caractères
* Balise `og:image` qui représente l'image qui sera affiché sur le post final. recommendations:
	* Ratio de l'image: 1.91:1
	* Résolution optimale 1200 x 630.
	* La taille de l'image ne doit pas dépasser les 8mb