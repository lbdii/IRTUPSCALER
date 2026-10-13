IRTUPSCALE
Extension Chrome d’amélioration vidéo en temps réel et d'export, avec upscale par IA locale et shaders accélérés par WebGPU.
IRTUPSCALE permet de personnaliser le rendu des vidéos directement dans le navigateur. Le traitement s’effectue sur votre appareil, sans envoyer les images à un serveur.

Attention : matériel graphique haut de gamme recommandé, les test pour un rendu en temps réel sont effectués sur RX9070XT, les résultats sont peut convaincant dès leurs que la résolution augmente, pour un résultat optimal il est recommandé d'utiliser la fonction d'export d'un fichier MP4 directement plutôt qu'une source Youtube.

Fonctionnalités 2.0 :
Export vidéo avec upscale
L’export permet de créer un nouveau fichier vidéo amélioré avec les réglages choisis dans IRTUPSCALE, enregistré sur ton ordinateur.
Contrairement au traitement pendant la lecture, l’export fonctionne hors temps réel : chaque image est traitée avant d’être encodée. Il peut donc prendre plus de temps que la durée de la vidéo, sans devoir sauter des images pour suivre la lecture.
Fonctionnement :
1. Choisir la source : un fichier vidéo local, comme un MP4, ou une vidéo YouTube. Depuis la barre IRTUPSCALE du lecteur, la vidéo courante est sélectionnée directement.
2. Définir le traitement : méthode de reconstruction, résolution, détail de calcul, force IA, couleurs et netteté.
3. Visualiser le résultat : afficher une image aléatoire, appliquer les paramètres à l’aperçu et comparer avec l’image source.
4. Choisir l’extrait et l’audio : définir le début et la fin, conserver la cadence source et utiliser sa piste audio lorsqu’elle est accessible. Un MP3 peut être importé si nécessaire.
5. Lancer l’export : les images sont traitées localement puis assemblées avec l’audio dans un fichier WebM.
La progression affiche la vitesse de traitement et le temps restant estimé. L’export peut être annulé.
À savoir : l’export ne transforme pas automatiquement une vidéo en 60 FPS. L’interpolation y est désactivée et le flou de mouvement est coupé par défaut. La qualité obtenue dépend de la source, du modèle et des réglages ; augmenter la résolution ne garantit pas davantage de détails.

Fonctionnalités d'upscale en temp réel :
- Upscale dédié à l’animation.
- Méthodes de redimensionnement via AMD FSR 1.
- Filtres personnalisables : netteté, débruitage, couleurs, gamma, contraste et réduction des artefacts.
- Options de fluidité : flou de mouvement et interpolation expérimentale.
Compatible avec les vidéos accessibles au traitement dans le navigateur, notamment sur YouTube et Dailymotion. Les performances dépendent du matériel, du modèle et des réglages choisis. Les vidéos protégées par DRM ne sont pas prises en charge.

Installation dans Chrome — mode développeur :
1. Téléchargez IRTUPSCALE-2.0.zip depuis la section Releases du dépôt.
2. Décompressez l’archive dans un dossier permanent.
3. Ouvrez Chrome et saisissez chrome://extensions dans la barre d’adresse.
4. Activez le Mode développeur, en haut à droite.
5. Cliquez sur Charger l’extension non empaquetée.
6. Sélectionnez le dossier IRTUPSCALE contenant le fichier manifest.json.
7. Actualisez les pages vidéo déjà ouvertes.

Utilisation :
Cliquez sur l’icône Extensions de Chrome, puis épinglez IRTUPSCALE pour y accéder facilement.
Depuis le menu de l’extension, vous pouvez :
- Activer ou couper l’upscale.
- Afficher ou masquer la barre de contrôle.
- Télécharger ou exporter une vidéo
- Ouvrir les paramètres de traitement vidéo.
