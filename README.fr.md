# Palais Mental

**Français** · [English](README.md)

Un outil de mémorisation par palais mental et répétition espacée, contenu dans **un seul fichier HTML**. Pas d'installation, pas de compte, pas de serveur à soi, pas de connexion requise.

Version 9.0 · **[romanin86.github.io/REPETITA](https://romanin86.github.io/REPETITA/)**

---

## Démarrage rapide

**En ligne** — ouvrez **[romanin86.github.io/REPETITA](https://romanin86.github.io/REPETITA/)** dans Firefox, Chrome ou Edge. C'est tout.

**Hors ligne** — dans l'application, Paramètres → Avancé → **Télécharger l'application**. Vous obtenez un seul fichier, `palais-mental-v9.0.html`, qui fonctionne sans connexion, depuis le disque ou une clé USB. Le même fichier est dans ce dépôt : `index.html`, et toutes les versions dans `APPLICATIONS/`.

**Au premier lancement**, l'accueil propose quatre portes : essayer avec un palais d'exemple, créer avec une IA, importer un tableur, créer à la main.

Pour vos élèves, l'application produit un **fichier de lecture** autonome, à distribuer comme n'importe quel fichier.

**Un mot vous échappe ?** Le **Glossaire**, dans le menu latéral, définit chaque terme de l'application en une phrase et dit où le trouver.

---

## Vie privée, hors ligne, sécurité

**Tout reste sur votre appareil.** Une fois la page chargée, l'application ne contacte aucun serveur : ni Google, ni mesure d'audience, ni police téléchargée, ni bibliothèque externe. Tout le nécessaire est dans le fichier.

**Tout fonctionne sans connexion**, application comme fichier élève : création, révision, rappels, lecture à voix haute avec les voix de l'appareil, import et export de tableurs, sauvegardes, archives ZIP.

Seules quelques fonctions **facultatives** passent par internet, et uniquement quand vous les déclenchez : la génération d'images, la recherche de photos libres et de définitions, les boutons qui ouvrent une IA depuis le générateur de prompt, et les voix en ligne de la lecture à voix haute, si vous les autorisez.

**Le contenu importé est traité comme non fiable.** Un tableur, une réponse d'IA collée ou une sauvegarde piégés ne peuvent pas exécuter de code : le texte est neutralisé avant affichage, et seules les adresses web `https://` ou `http://` peuvent être ouvertes.

---

## Plateformes et navigateurs

| Plateforme | Fichier ouvert depuis le disque | Le site, ou toute adresse web |
|---|---|---|
| **Windows, macOS, Linux — Firefox** | Complet | Complet |
| **Windows, macOS, Linux — Chrome, Edge** | Capacité réduite, voir ci-dessous | Complet |
| **Android — Firefox, Chrome** | Complet | Complet |
| **iPad, iPhone** | Non pris en charge | Non pris en charge |

**Chrome et Edge** refusent le stockage complet aux fichiers ouverts depuis le disque. L'application bascule alors sur un stockage de secours et l'annonce par un bandeau : tout fonctionne, mais la capacité tombe à quelques mégaoctets, vite insuffisante avec des images. Deux solutions : ouvrir le fichier avec **Firefox**, ou utiliser **le site**.

**Le fichier de lecture** n'a pas cette limite : la progression d'un élève pèse quelques kilooctets, le stockage de secours la conserve sans difficulté.

**Sur un lecteur réseau**, utilisez une lettre de lecteur (`Z:`) ou une adresse web, plutôt qu'un chemin `\\serveur\partage` que certains navigateurs bloquent. Les données ne sont jamais écrites sur le partage : chaque utilisateur a les siennes, sur son poste, et vingt élèves peuvent ouvrir le même fichier en même temps.

**Sur iPad et iPhone**, l'aperçu de l'app Fichiers n'exécute pas le JavaScript : l'application ne peut pas démarrer depuis un fichier local. Un message l'explique au lieu d'afficher une page vide.

---

## Deux formes

| | **L'application** | **Le fichier de lecture** |
|---|---|---|
| Pour qui | L'enseignant | Les élèves |
| Créer, modifier, supprimer | Oui | Non |
| Réviser, se programmer des rappels, écouter les fiches | Oui | Oui |
| Progression enregistrée | Sur votre appareil | Sur l'appareil de l'élève, sans jamais toucher à votre version |

---

# Première partie — L'application

## 1. La structure

Trois niveaux, du plus large au plus fin :

- **Palais** — une matière, un programme, un thème. *« Histoire-géographie 3e »*
- **Salle** — un chapitre, une notion. *« La Seconde Guerre mondiale »*
- **Objet** — une fiche, une chose à retenir. *« Débarquement de Normandie »*

Un objet porte un **titre** (la question), une **information à retenir** (la réponse), et éventuellement une **image**, une **phrase mnémotechnique**, des **étiquettes** et un **document joint**.

Le tri choisi sur l'accueil s'applique à toutes les listes de palais de l'application. Dans une salle qui contient des images, chaque fiche montre la sienne en vignette : toutes les cartes gardent la même taille.

## 2. Créer du contenu

Le bouton **Nouveau palais** propose toutes les voies :

- **Créer avec une IA** — le générateur de prompt, le plus simple pour débuter, voir la section suivante.
- **Coller la réponse d'une IA** — le tableau copié depuis la conversation, sans passer par un fichier ni par un tableur. Pratique sur téléphone.
- **Importer un tableur**, rempli à la main ou par une IA. Le modèle vierge se télécharge dans Paramètres → Créer et organiser le contenu → Import / export tableur. Une ligne = une fiche ; les palais et salles manquants sont créés à l'import.
- **Créer à la main**, palais par palais.
- **Le palais d'exemple**, qui fait découvrir l'application en s'en servant.

On peut aussi **importer une sauvegarde** ou une archive, en JSON ou en ZIP.

**Une IA livre rarement un tableau parfait** : bloc de code, phrase avant et après, tableau markdown, colonnes vides oubliées. Le collage et l'import de `.csv` rattrapent ces défauts. Ce qui reste ambigu — une colonne de trop ou de moins au milieu d'une ligne — est **écarté et signalé**, jamais importé de travers.

**Après un import**, un bilan confirme que tout est enregistré — nombre de fiches, détail par palais, lignes écartées — et propose, **en option**, d'ajouter des images, avec une estimation de la durée. On peut aussi le faire plus tard.

## 3. Le générateur de prompt

Il rédige pour vous la demande à faire à une IA. Menu latéral → **Générateur de prompt**.

**D'abord, l'approche :**

| Approche | Ce qu'elle produit | Réglages propres |
|---|---|---|
| **Mémoriser** | Des fiches courtes et indépendantes : vocabulaire, dates, définitions, formules | Types de contenu ; en Expert, lignes « Méthode » et « Piège », mnémotechniques, longueur des réponses |
| **Comprendre pour retenir** *(expérimental)* | Une suite de questions qui s'appuient les unes sur les autres — pourquoi, comment, que se passe-t-il si… Les salles deviennent les étapes d'une progression | Types de questions, modifiables (« Gérer ») ; en Expert, prérequis, lignes « Défi » et « Explique », colonne mnémo, longueur des explications |
| **Raconter une histoire** *(expérimental)* | Le palais devient le décor d'un récit : chaque salle est un lieu que traverse le héros. Le passage de l'histoire se lit en parcours et sert d'indice en révision, la réponse masquée | Genre, héros, apprentissage d'une langue étrangère (récit en français ou dans la langue apprise, niveau A1 à B2) ; en Expert, longueur des passages |
| **Phrases pas à pas** *(expérimental)* | Des phrases simples, de plus en plus longues, que l'élève reconstruit en remettant les mots dans l'ordre. Chaque salle est un palier. Pour l'ULIS, le FLE, le cycle 2 | Niveau de lecture (du CP au cycle 3), distinct de l'âge du public ; paliers ; longueur des phrases ; constructions à travailler ; prénoms des personnages ; au-dessus des mots : une question, une situation à comprendre ou un titre ; en Expert, indice et temps des verbes |

**Puis le niveau de personnalisation :**

| Niveau | Ce qu'on remplit |
|---|---|
| **Express** | Le sujet, le public, le nombre de fiches — ou « L'IA estime ». L'IA propose le reste. |
| **Guidé** — *par défaut* | + nom du palais, salles, réglages propres à l'approche, images, favoris |
| **Expert** | + réglages avancés de l'approche, style d'image, référence à suivre, exclusions |

**Les règles d'une bonne fiche sont ajoutées d'office**, à tous les niveaux : un titre qui ne contient jamais la réponse, des réponses toutes différentes pour la révision à l'envers, l'interdiction d'inventer, aucune carte ni sujet douloureux en image. Pour « Phrases pas à pas », s'y ajoute la règle d'or : une seule façon correcte d'ordonner les mots de chaque phrase.

**Adapter pour**, à tous les niveaux :
- cinq cases qui se cumulent : **dyslexie et dysorthographie, dyscalculie, dyspraxie, dysphasie, troubles de l'attention** ;
- **élèves allophones (FLS)** : 35 langues d'origine au choix, plus une langue libre, et le niveau de français de A1 à B1. L'IA ajoute la traduction et, si besoin, une transcription en alphabet latin. Faites-la relire par un locuteur quand c'est possible.

**Le résultat** se met à jour en direct. « Copier le prompt », « Télécharger le modèle vierge », puis huit IA — Duck.ai, ChatGPT, Copilot, Perplexity, Claude, Gemini, Le Chat, DeepSeek : chaque bouton copie le prompt puis ouvre le site. Il reste à joindre le modèle vierge et coller. Les IA marquées **« sans compte »** s'utilisent sans se connecter, avec un nombre de messages limité. **« Gérer les IA »** permet de modifier, masquer ou ajouter des IA, y compris celles d'origine.

**Pour les IA gratuites** qui ne savent pas produire de fichier, le prompt leur demande un tableau CSV à points-virgules : copiez-le, puis **« Coller la réponse de l'IA »**.

**La bibliothèque** conserve vos prompts : les recharger dans le formulaire, les renommer, les modifier, les copier, les supprimer.

## 4. Affiner le contenu

Un contenu généré est globalement juste, jamais parfait. Le mode **Parcourir** fait défiler les fiches sans interrogation : c'est le mode de relecture.

- **Modifier** corrige la fiche et vous ramène à la même carte.
- **L'étoile** marque ce qui mérite d'être gardé.

**Le circuit de curation**, pour extraire le meilleur d'un gros palais généré :

1. Dupliquer le palais (menu « Plus »)
2. Parcourir la copie en étoilant ce que vous gardez
3. Dans une salle, cliquer **Favoris** jusqu'à afficher **« Non favoris »**
4. Tout sélectionner, supprimer

La suppression reste annulable douze secondes, et un instantané est pris avant.

## 5. Les images

Trois sources, pour une fiche ou pour un lot :

- **Génération par IA** — Pollinations.ai, gratuit, sans compte, clé facultative
- **Photo libre** — Openverse, Wikimedia Commons ; l'auteur, la source et la licence sont conservés
- **Import** depuis votre appareil

**Le style compte plus que tout.** « Fidèle au sujet » illustre la notion ; les autres styles créent des scènes décalées, efficaces pour un mot isolé. En lot, le style est fixé pour toute la série.

**Images en lot** : Paramètres → Images et services en ligne → Images en lot, ou menu « Plus » d'un palais.

## 6. Les documents joints

Chaque fiche peut porter un PDF ou un document bureautique. Le PDF s'ouvre pendant la révision, même hors connexion ; les autres formats s'ouvrent dans le logiciel de l'élève. Un import en lot associe chaque fichier à la fiche dont le titre correspond à son nom.

## 7. Réviser

La révision est espacée : une fiche sue revient plus tard, une fiche manquée revient vite.

**Au-dessus de chaque question**, une ligne indique d'où vient la fiche — *● Histoire-géographie 3e › La Seconde Guerre mondiale* — avec la couleur du palais. On sait toujours où l'on est, même dans une révision qui mélange plusieurs salles.

**Que faut-il deviner ?** Quatre types de question :

| Type | Ce qui est montré | Ce qu'on retrouve |
|---|---|---|
| **Le nom de l'objet** | L'image et l'information | Le titre |
| **L'information à retenir** | Le titre | La réponse |
| **Tout, à partir de l'emplacement** | La salle et le rang seulement, comme dans un vrai palais mental | Tout |
| **Remettre les mots dans l'ordre** | Les mots de la réponse, mélangés | La phrase, voir la section suivante |

**Les réglages de la révision** : type de question, ordre aléatoire, indice automatique, lecture automatique, images. Pendant une révision : modifier la fiche, l'étoiler, **la mettre de côté** pour reprendre plus tard. Une session interrompue est proposée à la reprise au retour.

**Au clavier** : Espace ou Entrée révèle la réponse, puis 1, 2, 3, 4 pour Encore, Difficile, Bien, Facile.

## 8. Remettre les mots dans l'ordre

La phrase à retenir arrive en **étiquettes mélangées** ; l'élève les touche dans l'ordre. La majuscule du premier mot et le point final restent sur les étiquettes : ce sont des indices, comme dans les exercices de classe.

**La correction est automatique, en deux essais.** Au premier essai faux, les mots bien placés restent, marqués ✓. Juste du premier coup, la fiche compte « Bien » ; au deuxième essai, « Difficile ». Ratée deux fois, ou abandonnée avec « Voir la réponse », la phrase s'affiche corrigée et revient un peu plus tard dans la séance.

**Pour l'activer :**
- la colonne `exercice` du tableur, à `ordre` — c'est ce que produit l'approche « Phrases pas à pas » ;
- la case **« En révision, remettre les mots dans l'ordre »** d'une fiche ;
- menu « Plus » d'un palais → **« Réviser en remettant les mots dans l'ordre »**, pour tout un palais ;
- ou, pour une seule révision, le type de question **« Remettre les mots dans l'ordre »**, sur n'importe quel palais.

Une information trop courte ou trop longue — moins de 3 ou plus de 20 étiquettes — ou écrite sur plusieurs lignes reste une question habituelle.

> L'application n'accepte que l'ordre exact de la phrase écrite. Une phrase qui s'ordonne de deux façons correctes — « Léo lit le soir » et « Le soir, Léo lit » — comptera faux. Relisez les phrases produites par une IA.

## 9. La lecture à voix haute

Un bouton haut-parleur apparaît à côté des titres et des réponses : en révision, en parcours, dans les fiches et dans le fichier élève. La **langue** se règle pour chaque palais, et une salle peut en changer ; treize langues sont proposées. Paramètres → Apparence → **Lecture à voix haute** : vitesse, lecture automatique de la réponse, voix en ligne facultatives, et un bouton pour tester chaque voix.

Les voix sont celles de l'appareil : une voix absente s'installe dans les réglages du système. Chaque appareil a les siennes — vérifiez celles de la salle informatique.

## 10. Les favoris

L'étoile marque une fiche — dans une salle, en révision ou en parcours. Menu latéral → **Favoris** pour les réviser tous, palais confondus ; **« Parcourir les favoris »** pour les relire sans interrogation.

Le filtre d'une salle a trois états : tous, favoris, non favoris. **Retrait en masse** dans Paramètres → Créer et organiser le contenu → Favoris.

## 11. Les rappels

Une série de rappels programme des révisions à dates précises : ce qu'il faut revoir, un point de départ, des délais — J+1, J+3, J+7…

Séries prêtes : **Courbe de l'oubli**, **Progressive**, **Hebdomadaire**, **Avant examen**. Toutes modifiables. L'**Agenda** présente un calendrier à pastilles colorées.

L'application ne peut pas envoyer de notification elle-même : elle n'a pas de serveur. Elle crée un **fichier d'agenda** que votre calendrier importe, avec une entrée par échéance, ou prépare un **courriel** déjà rédigé.

## 12. Imprimer

Menu « Plus » d'un palais ou d'une salle → **Imprimer**. Deux types de fiche : **complète** — nom, information à retenir et mnémotechnique, à relire — ou **d'entraînement** — les noms seuls, suivis de lignes vierges, pour s'interroger par écrit. Les images et les mnémotechniques sont facultatives.

## 13. Sauvegarder, archiver

Paramètres → Exporter et sauvegarder :

- **Sauvegarde & transfert** — la **sauvegarde complète**, en JSON ou en ZIP : palais, images, documents, progression, rappels, fond d'écran, services, bibliothèque de prompts, IA et types de questions modifiés. Et l'**archive de palais choisis**, sans aucun réglage : la réimporter ne touche à rien d'autre.
- **Sauvegardes automatiques** — des instantanés pris avant chaque opération risquée, restaurables.

> Les clés d'accès aux services ne sont **jamais** exportées.

**Passer du site à une copie hors ligne**, ou l'inverse : les données sont liées à l'adresse, et la copie démarre vide. Faites une sauvegarde complète, puis importez-la dans la copie.

## 14. Importer une grosse base

Pendant un import, une fenêtre montre l'étape en cours, la progression et une estimation du temps restant. À la fin, un bilan situe la base : **confortable** sous 3 000 fiches, **chargée** jusqu'à 8 000, **lourde** au-delà. Ce sont des repères estimés, pas des limites : au-delà, tout fonctionne, plus lentement sur téléphone. Archivez alors les matières inactives.

## 15. Exporter pour les élèves

Paramètres → Exporter et sauvegarder → **Exporter en lecture seule** :

1. Dépliez **« Choisir les palais »** et cochez ceux à distribuer
2. Vérifiez la **taille estimée** et l'indicateur de confort
3. Choisissez un nom, ou une des propositions
4. Cochez **« Réinitialiser les statistiques »** si le fichier est pour quelqu'un d'autre
5. Gardez ou non le fond d'écran, puis générez

Le fichier élève s'ouvre avec vos tris d'affichage ; l'élève peut les changer.

| Taille | Ce que ça donne |
|---|---|
| moins de 8 Mo | Confortable partout |
| 8 à 25 Mo | Ouverture un peu lente sur appareil ancien |
| 25 à 60 Mo | Envoi par messagerie souvent refusé |
| plus de 60 Mo | Risque de blocage sur téléphone |

**Après une correction, régénérez et redistribuez** : un fichier déjà distribué ne se met pas à jour tout seul.

## 16. Le fond d'écran

Paramètres → Apparence → Fond d'écran, trois onglets : **Générer (IA)**, **Photo libre**, **Importer**. Un clic place une image en aperçu ; votre fond actuel reste en place jusqu'à **« Appliquer ce fond »**, et **« Revenir au fond précédent »** annule.

## 17. Paramètres, explications et glossaire

Les Paramètres sont rangés sous **cinq thèmes**, chacun avec sa couleur : créer et organiser le contenu, images et services en ligne, exporter et sauvegarder, apparence, avancé. Chaque section affiche **un résumé d'une ligne**, même repliée.

**Apparence** : deux thèmes, Nocturne et Parchemin, et la taille du texte de lecture. **Avancé** : télécharger l'application, l'état du stockage, et un **diagnostic** à transmettre en cas de problème — il ne contient aucun contenu personnel, seulement des nombres et des messages techniques.

**Les explications détaillées sont masquées** et s'ouvrent section par section avec le **« ? »**. Pour les afficher partout : Apparence → **« Toujours afficher les explications »**.

**Le Glossaire** — menu latéral — définit près de cinquante termes en cinq familles, avec une recherche et, pour chaque mot, où le trouver. **La Progression** — menu latéral — montre où en est la mémorisation, palais par palais.

---

# Deuxième partie — Le fichier de lecture

*À transmettre aux élèves.*

## Ouvrir

Double-cliquez sur le fichier. Il s'ouvre dans votre navigateur. **Aucune connexion nécessaire**, et rien n'est envoyé nulle part.

Si un message dit que le fichier ne peut pas s'ouvrir ici, c'est qu'il est affiché dans un simple aperçu : ouvrez-le avec Firefox, Chrome ou Edge.

## Ce qu'on peut faire

**Parcourir** les palais, les salles et les fiches, et **chercher** un mot. **Réviser** : une question, vous cherchez, vous révélez, vous indiquez si vous saviez — ou vous remettez les mots dans l'ordre, et la correction est automatique. La ligne au-dessus de la question rappelle toujours le palais et la salle. **Écouter** les titres et les réponses. **Mettre de côté** une révision pour la reprendre plus tard. **Se programmer des rappels**, et les envoyer dans son agenda. **Trier les palais**.

## Ce qu'on ne peut pas faire

Créer, modifier ou supprimer. Le contenu est celui que votre enseignant a validé.

## Votre progression

Elle est enregistrée **dans votre navigateur, sur votre appareil**, et ne remonte à personne. Vous la retrouvez en rouvrant le fichier sur le même appareil et le même navigateur ; elle ne vous suit pas sur un autre poste.

Si le navigateur refuse tout enregistrement, un bandeau vous prévient **avant** que vous ne révisiez pour rien.

---

# Troisième partie — Référence technique

## Formats acceptés

| Usage | Formats |
|---|---|
| Import de contenu | `.xlsx`, `.ods`, `.csv` (virgules ou points-virgules), tableau collé (CSV, markdown ou tabulations), `.json`, `.zip` |
| Images | `.jpg`, `.png`, `.webp`, `.gif` |
| Documents joints | `.pdf`, `.docx`, `.doc`, `.odt`, `.xlsx`, `.xls`, `.ods`, `.csv`, `.rtf`, `.txt` |

## Colonnes du tableur

| Colonne | Contenu |
|---|---|
| `palais`, `salle`, `objet` | Obligatoires. Les palais et salles manquants sont créés |
| `contenu` | L'information à retenir |
| `mnemo` | La phrase mnémotechnique, ou l'indice |
| `prompt` | Une description d'image propre à la fiche, prioritaire sur le style |
| `tags` | Les étiquettes, séparées par des virgules |
| `favori` | `oui` ou `non` |
| `image` | Une adresse `https://` d'image à récupérer, ou vide |
| `exercice` | Facultative : `ordre` fait remettre les mots dans l'ordre en révision |

Réimporter un tableur met à jour les fiches de même titre, dans la même salle.

## Limites

- **Document joint** : avertissement au-delà de 2 Mo, refus au-delà de 12 Mo
- **Images** : redimensionnées à 640 px ; fond d'écran à 1600 px
- **Fichier de lecture** : au-delà de 25 Mo, envoi par messagerie souvent refusé
- **Mots dans l'ordre** : de 3 à 20 étiquettes, ponctuation finale comprise

## Où sont les données

Dans le stockage du navigateur, **par adresse** et non par fichier : deux copies de l'application ouvertes depuis la même adresse partagent la même base ; le site et une copie téléchargée ont chacun la leur. Les données survivent à la fermeture, mais pas à un effacement des données du navigateur ni à un changement d'appareil.

**Exportez régulièrement.** C'est la seule vraie sauvegarde.

## Services d'images

- **Pollinations** — génération par IA. Délai imposé par le service gratuit : environ **16 secondes** pour une image, **23 par image en lot**. Avec une clé : 6 et 9 secondes.
- **Photos libres** — Openverse, Wikimedia Commons, et d'autres services à déclarer dans Paramètres → Images et services en ligne → Clés d'accès aux services.

## En cas de problème

| Symptôme | À vérifier |
|---|---|
| Bandeau « Stockage réduit dans ce navigateur » | Chrome ou Edge sur un fichier local : ouvrez-le avec Firefox, ou utilisez le site |
| Message « ne peut pas s'ouvrir ici » | Le fichier est affiché dans un aperçu : ouvrez-le dans Firefox, Chrome ou Edge |
| Le fichier élève n'affiche rien | Il vient d'une version ancienne : régénérez-le |
| Des lignes écartées à l'import | La réponse de l'IA est mal formée à ces endroits : le bilan les cite, corrigez-les ou redemandez-les |
| Les phrases ne se mélangent pas en révision | L'IA a oublié la colonne `exercice` : menu « Plus » du palais → « Réviser en remettant les mots dans l'ordre » |
| Une voix ne lit pas | Elle n'est pas installée sur cet appareil : Paramètres → Lecture à voix haute |
| La génération d'image échoue | Un VPN est souvent bloqué par le service, de même qu'une clé dont le compte est épuisé |
| Des favoris jamais posés | Ils viennent du tableur importé : retrait en masse dans Paramètres → Favoris |
| L'application est lente sur téléphone | Voir le bilan de volume : archivez les matières inactives |
| Une suppression regrettée | Le bandeau d'annulation (douze secondes), sinon un instantané |
| Un comportement inattendu | Paramètres → Avancé → Diagnostic : le rapport à transmettre |

## Limites connues

- **iPad et iPhone** : non pris en charge.
- **Chrome et Edge sur un fichier local** : capacité de stockage réduite, voir « Plateformes et navigateurs ».
- **Mots dans l'ordre** : un seul ordre est accepté, celui de la phrase écrite.
- **SheetJS 0.18.5**, intégré pour lire les tableurs, présente des failles connues à l'import de fichiers piégés. N'importez pas de tableur d'origine inconnue.

## Contenu du dépôt

| Dossier ou fichier | Contenu |
|---|---|
| `index.html` | L'application, version en cours — celle que sert le site |
| `APPLICATIONS/` | Les versions publiées, de la 6.0 à la 9.0 |
| `READERS/` | Des fichiers élève d'exemple : français pour touristes, cybersécurité, FLS, démonstration collège |
| `SPREADSHEET/` | Des palais prêts à importer : dix matières du collège, de la 6e à la 3e (`Claude/`), et des tableurs produits avec DeepSeek (`INBULK/`) |
| `PROMPTS/` | Des exemples de prompts et des tableurs obtenus |
| `GETTING_STARTED_GUIDE/` | Le fichier modèle (`.xlsx`, `.ods`), des prompts prêts à l'emploi, un tutoriel en image |
| `JSONS/` | Des sauvegardes de démonstration, à importer |
| `manifeste fr.png`, `manifest.png` | Le manifeste du projet : pourquoi et comment l'application est née |

## Bibliothèques tierces

Intégrées au fichier, sous leurs licences respectives :

| Bibliothèque | Version | Licence |
|---|---|---|
| Vue | 3.4 | MIT |
| SheetJS | 0.18.5 | Apache-2.0 |
| PapaParse | 5.3.0 | MIT |
| JSZip | 3.10.1 | MIT ou GPLv3, au choix |

## Licence

MIT — voir le fichier `LICENSE`.
