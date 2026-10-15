IRTUPSCALE — Amélioration vidéo et audio en local

IRTUPSCALE est une extension Chrome permettant d’améliorer l’image et le son des vidéos directement dans le navigateur, pendant leur lecture ou lors d’un export vers un nouveau fichier.
L’extension combine des modèles d’intelligence artificielle exécutés localement, des filtres vidéo accélérés par WebGPU et des traitements audio. Elle propose deux usages complémentaires :
- En temps réel : ajuster l’image et le son d’une vidéo pendant son visionnage.
- À l’export : traiter chaque image avec les paramètres choisis et enregistrer le résultat en MP4 ou WebM, avec sa piste audio.
Les modèles sont inclus dans l’extension. Aucune image ni piste audio n’est envoyée à un serveur de traitement.

Amélioration vidéo en temps réel 
IRTUPSCALE affiche une barre de commandes auprès des lecteurs vidéo compatibles. Le traitement peut être activé ou désactivé sans modifier le fichier source.

Méthode	Utilisation 
None :Appliquer uniquement les filtres compatibles, à la résolution source, sans reconstruction IA.
IA locale : contours	Mode par défaut utilisant NomosUni compact. Conseillé pour les contours d’animation ; peut donner un aspect dessiné aux images réelles.
AnimeJaNai V3 : animation	Modèle spécialisé pour les animes et les dessins animés.
Images réelles : naturel — expérimental	Modèle Real-ESRGAN general WDN, à débruitage faible, destiné aux films, documentaires et visages. Plus exigeant en calcul.
Une nouvelle vidéo démarre sans upscale actif. Les réglages restent enregistrés pour les utilisations suivantes.

Réglages de reconstruction 
- Détail de calcul pour choisir la quantité de pixels analysés par l’IA.
- Force IA pour doser la contribution du modèle.
- Limitation des défauts pour atténuer les différences excessives avec la source.
- FP16 automatique ou FP32, selon le modèle et les capacités du GPU.
- Préparation de l’IA avant la reprise de la lecture pour limiter les saccades d’initialisation.
La résolution de sortie et le détail analysé sont deux paramètres distincts. Augmenter les dimensions ne garantit pas la reconstruction de détails supplémentaires.

Agrandissement final FSR1 
Le mode IA locale peut utiliser AMD FSR1/EASU pour agrandir le résultat après le traitement IA.
La chaîne de traitement est la suivante :
Source adaptée au détail choisi → IA locale → agrandissement final FSR1 → filtres de sortie.
La réduction du travail IA peut améliorer les performances, au prix d’une diminution des informations analysées. FSR1 n’accélère pas directement le modèle.
Cette option est réservée à l’IA locale en temps réel. La netteté RCAS reste réglable séparément.

Filtres vidéo et mouvement 
Les effets peuvent être activés et ajustés individuellement :
- Couleur et gamma : luminosité, contraste, saturation, température et gamma.
- Netteté adaptative RCAS.
- Netteté Unsharp Mask.
- Contraste local.
- Débanding et grain pour atténuer les bandes de couleur.
- Débruitage bilatéral.
- Réduction des blocs de compression.
- Compensation temporelle expérimentale.
- Flou de mouvement léger.
- Interpolation optique expérimentale en temps réel.
Les filtres incompatibles avec la méthode sélectionnée sont désactivés avec une explication. Le flou de mouvement et l’interpolation s’excluent.
L’interpolation et le flou peuvent modifier la perception du mouvement, mais n’augmentent pas la vitesse de calcul de l’IA.

Barre de commandes intégrée 
La même barre compacte à icônes est utilisée sur les différents sites et en plein écran.
Elle donne accès à :
- L’activation du traitement vidéo.
- La fenêtre des paramètres vidéo.
- La page d’export.
- Une fenêtre audio indépendante.
- L’affichage des statistiques.
- Un cadenas de maintien à l’écran.
- Le masquage de la barre.

Positionnement et affichage 
- Sur YouTube, placement sous le titre lorsque l’espace disponible le permet, sans décaler la description.
- Adaptation aux modes normal, cinéma et plein écran.
- Sur les autres lecteurs, placement hors de la vidéo lorsque possible, sinon au-dessus de la zone basse des commandes.
- Conservation du cadrage, des proportions et des couches du lecteur.
- Déplacement manuel avec la poignée.
- Recentrage par double-clic ou avec la touche Début/Home.
- Déplacement au clavier avec les flèches.
Le cadenas est activé par défaut pour garder la barre visible. Lorsqu’il est désactivé, la barre située dans le lecteur suit le masquage des commandes YouTube ou se masque après inactivité sur les autres sites.
Les statistiques affichent uniquement la résolution sélectionnée et les FPS réellement traités. Leur visibilité est mémorisée.

Amélioration audio en temps réel 
Le traitement audio possède son propre interrupteur et une fenêtre de réglages séparée.
Il peut fonctionner même lorsque l’upscale vidéo est désactivé.
Les réglages disponibles sont :
- Atténuation des bruits faibles.
- Clarté des voix par égalisation.
- Équilibrage du volume par compression douce.
- Gain réglable.
- Limiteur de pics à −0,5 dBFS.
- Réinitialisation du profil audio.
Le traitement en direct utilise des filtres CPU légers. Les changements s’appliquent immédiatement ; la désactivation rétablit une voie audio transparente.

Ajustement automatique 
L’extension peut analyser le son source pour proposer des réglages adaptés à ses caractéristiques :
- Niveau moyen et pics.
- Variations de volume.
- Répartition de l’énergie dans les fréquences.
Une explication accompagne les choix appliqués.
L’analyse rapide observe environ six secondes. L’option Ajustement plus précis observe jusqu’à trente secondes de lecture.
Cette analyse repose sur les mesures sonores : elle ne reconnaît pas automatiquement le genre ou l’ancienneté du contenu.

Export vidéo 
L’export crée un nouveau fichier avec les réglages vidéo et audio choisis. Contrairement au rendu en direct, il peut prendre le temps nécessaire pour traiter chaque image.

Sources disponibles 
- Fichier vidéo local : MP4, M4V, MKV, WebM ou MOV.
- Lien YouTube depuis le sélecteur de source.
- Vidéo courante lorsqu’on ouvre l’export depuis la barre du lecteur.
La prise en charge dépend du conteneur et des codecs réellement décodables par Chrome sur l’appareil. Un fichier MKV, par exemple, peut contenir un codec non pris en charge.

Formats de sortie 
Format	Vidéo	Audio
MP4 — par défaut	H.264	AAC
WebM	AV1, VP9 ou VP8 selon disponibilité	Opus
Le fichier peut être écrit directement dans une destination choisie ou proposé au téléchargement après sa préparation.

Paramètres d’export 
- Début et fin en minutes décimales, avec rappel en minutes et secondes.
- Résolution, détail, précision et contribution de l’IA.
- Filtres vidéo compatibles.
- Conservation de la cadence source lorsqu’elle est connue, ou cadence manuelle.
- Débit vidéo.
- Choix et amélioration de l’audio.
- Activation indépendante du traitement vidéo.
L’interpolation est désactivée à l’export. Le flou de mouvement est désactivé par défaut, mais reste disponible en option.

Modèles supplémentaires pour l’export 
Deux modèles plus exigeants complètent ceux disponibles en direct :
- Real-ESRGAN ×4 · vidéo réelle.
- Real-ESRGAN AnimeVideo v3 ×4 · animation.
Ils utilisent une reconstruction native ×4 et un traitement par tuiles avec chevauchement pour limiter la mémoire d’inférence.

Aperçu avant export 
La page d’export permet de comparer les réglages avant de lancer un traitement long :
- Nouvelle image : sélectionner une image aléatoire de l’extrait.
- Appliquer à l’aperçu : recalculer la même image avec les nouveaux paramètres.
- Comparer à la source : afficher la trame source correspondante.
- Plein écran : agrandir l’aperçu sans étirement.
Les commandes de comparaison restent accessibles dans l’aperçu en plein écran.

Audio à l’export 
Plusieurs sources audio sont proposées :
- Piste du fichier vidéo local.
- Piste directement accessible de la vidéo en ligne.
- MP3 ou fichier audio importé.
- Capture volontaire du son de l’onglet.
- Export sans audio.
Les images et le son utilisent les mêmes bornes temporelles.

Traitements disponibles
En plus des filtres légers du temps réel, l’export propose :
- RNNoise : débruitage neuronal destiné aux voix.
- NovaSR : reconstruction estimée des hautes fréquences vocales, avec intensité réglable.
Ces options peuvent modifier la musique et les effets sonores. Elles restent désactivées par défaut et doivent être comparées à la source.

Analyse et aperçu sonore
- Extrait aléatoire de six secondes maximum.
- Renouvellement du passage.
- Application des réglages sur le même extrait.
- Écoute de la source et du résultat traité.
- Analyse automatique rapide ou de toute la plage d’export avec l’option précise.
- Suggestions d’IA vocales soumises à une activation explicite.
La préécoute nécessite une piste directement lisible ou un fichier audio importé.

Progression, annulation et reprise
Le suivi affiche notamment :
- Le nombre d’images calculées.
- La vitesse de traitement.
- Le temps écoulé et le restant estimé.
- La durée audio réellement traitée.
- Les étapes de chargement et de finalisation.
Annuler et garder le résultat partiel produit un fichier lisible des images déjà encodées, avec l’audio limité à leur durée.
Il est ensuite possible de :
- Reprendre l’export d’origine, sans recalculer les images sauvegardées.
- Modifier les paramètres pour commencer un nouvel export.
- Changer de source.
La reprise exige de garder la page d’export ouverte. Elle ne survit pas à sa fermeture ou au redémarrage de Chrome.
L’ouverture de l’export coupe l’upscale en direct pour éviter deux traitements vidéo simultanés.

Performances et arrière-plan
IRTUPSCALE utilise notamment :
- WebGPU pour les modèles et les filtres vidéo.
- Des workers CPU pour le traitement audio.
- La préparation audio en parallèle du calcul vidéo lorsque la source le permet.
- Le préchargement de l’image suivante.
- Des files de traitement et un stockage temporaire bornés.
Pour YouTube, l’option Continuer en arrière-plan utilise un partage volontaire de l’onglet source afin de maintenir son rendu actif. Les images partagées ne servent pas à produire la vidéo exportée : les trames originales restent utilisées.
Une option permet également de mettre l’export en pause lorsque la source est masquée.
Les onglets doivent rester ouverts, le partage actif et l’ordinateur éveillé. Ce fonctionnement dépend de Chrome ; le comportement d’une fenêtre Windows réellement réduite n’a pas été validé de bout en bout. Une source locale reste généralement plus prévisible qu’un lecteur en ligne.

Confidentialité
- Traitement des images et du son sur l’appareil.
- Modèles inclus dans l’extension.
- Aucun compte requis.
- Aucune publicité ni télémétrie intégrée.
- Aucun envoi des médias vers un serveur d’amélioration.
- Préférences enregistrées localement dans Chrome.
- Aucun accès au microphone.
- Partage d’onglet uniquement à la demande de l’utilisateur.
Les sites vidéo et leurs serveurs média conservent leur propre fonctionnement réseau.

Compatibilité et limites
IRTUPSCALE nécessite Chrome avec WebGPU, l’accélération graphique active et une vidéo dont le navigateur autorise l’accès aux pixels.
- La compatibilité varie selon les lecteurs, les codecs, le GPU et les pilotes.
- Les contenus protégés par DRM, notamment les programmes Netflix protégés, ne sont pas compatibles avec le traitement ou l’export.
- Aucun contournement DRM n’est intégré.
- Les directs et les publicités ne sont pas exportés.
- Les modèles peuvent modifier les textures, créer des artefacts ou du scintillement.
- Une résolution plus élevée ou un fichier plus volumineux ne garantit pas davantage de détails fidèles.
- Aucune cadence de 30/60 FPS ni occupation GPU maximale n’est garantie.
- Les réglages de qualité choisis ne sont pas diminués automatiquement pour accélérer le traitement.

Installation
1. Télécharger et décompresser le ZIP de la version souhaitée.
2. Ouvrir chrome://extensions.
3. Activer le Mode développeur.
4. Cliquer sur Charger l’extension non empaquetée.
5. Sélectionner le dossier IRTUPSCALE contenant manifest.json.
6. Actualiser les pages vidéo.
Pour une mise à jour, remplacer les fichiers dans le dossier déjà chargé, recharger l’extension puis actualiser les pages vidéo.

Technologies et licences
IRTUPSCALE s’appuie notamment sur WebGPU, ONNX Runtime Web, WebCodecs, AudioWorklet, AMD FSR1 et plusieurs modèles vidéo et audio locaux.
Les composants possèdent leurs propres licences, conservées dans la distribution.
Le paquet incluant AnimeJaNai est destiné à une distribution non commerciale, ses poids étant soumis à CC BY-NC-SA 4.0. La licence MIT du code ne remplace pas les conditions des modèles et composants tiers.
Consulter les fichiers LICENSE, THIRD-PARTY.md et les notices des modèles avant redistribution.
