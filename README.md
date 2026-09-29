### Détection de Mouvement par Caméra

Ce projet consiste en un simple fichier HTML qui utilise la caméra de l'utilisateur pour détecter les changements d'image (mouvement) et déclencher une alerte vocale.

#### Fonctionnalités :
*   Accède au flux vidéo de la caméra de l'utilisateur.
*   Affiche le flux vidéo dans un élément `<video>`.
*   Compare en continu les images successives du flux vidéo sur un `<canvas>` caché.
*   Détecte le mouvement en calculant la différence entre les pixels des frames.
*   Déclenche une **alerte vocale "Tu as été vu !"** si un mouvement significatif est détecté. Un message d'alerte traditionnel est utilisé comme solution de repli si la synthèse vocale n'est pas prise en charge par le navigateur.
*   Comprend un mécanisme de "cooldown" pour éviter des alertes trop fréquentes.

#### Comment l'utiliser :
1.  Enregistrez le contenu du fichier `index.html` dans un fichier nommé `index.html`.
2.  Ouvrez ce fichier `index.html` dans un navigateur web moderne (Chrome, Firefox, Edge, Safari).
3.  Le navigateur vous demandera l'autorisation d'accéder à votre caméra. Vous devez l'autoriser pour que l'application fonctionne.
4.  Une fois la caméra active, tout mouvement significatif devant la caméra déclenchera une alerte vocale. Assurez-vous que le son de votre appareil est activé.

#### Configuration :
Vous pouvez ajuster la sensibilité de la détection de mouvement en modifiant les variables JavaScript suivantes dans le fichier `index.html` :

*   `pixelThreshold` : Seuil de différence par composante de couleur (0-255). Une valeur plus faible rend la détection plus sensible aux petits changements de couleur.
*   `changedPixelsPercentage` : Pourcentage de pixels qui doivent être considérés comme "modifiés" pour déclencher une alerte. Une valeur plus faible rend la détection plus sensible aux mouvements étendus.
*   `alertCooldown` : Temps en millisecondes pendant lequel l'alerte ne sera pas répétée après avoir été déclenchée.

**Note de compatibilité :** L'alerte vocale utilise l'API Web Speech Synthesis. Sa prise en charge peut varier selon les navigateurs et les systèmes d'exploitation. Si l'API n'est pas disponible, une alerte textuelle traditionnelle sera affichée.

**Note de sécurité :** Cette application accède à votre caméra. Assurez-vous de comprendre le code avant de l'utiliser, surtout si vous modifiez la source.
