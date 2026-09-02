# ONTU-BF — Maquettes du portail et de l'application de collecte

Maquettes navigables produites dans le cadre de l'étude de mise en place de l'Observatoire National des Transports Urbains du Burkina Faso (ONTU-BF), Livrables 2 et 3, volet Architecture IT.

**Ce sont des maquettes.** Elles servent à valider des choix fonctionnels avant écriture du cahier des charges de réalisation. Les valeurs affichées sont des données de démonstration : aucune ne provient d'un producteur réel et aucune ne doit être citée.

## Contenu

| Fichier | Contenu |
|---|---|
| `index.html` | Portail de l'Observatoire : site public, connexion, six vues par profil |
| `mobile.html` | Application de collecte de terrain : cinq écrans, trois catégories de collecteurs |

**Pour voir les vues internes**, cliquer sur « Se connecter » en haut à droite, puis choisir un profil. Aucun mot de passe n'est vérifié. Le sélecteur en bas à droite permet de basculer directement d'un profil à l'autre, et « Vue publique » ramène au site.

Six profils sont simulés, chacun avec trois onglets et un contenu propre :

| Profil | Ce qu'il voit |
|---|---|
| Décideur | Synthèse nationale, comparaison des villes, alertes de niveau élevé |
| Exploitant | État des flux reçus, alertes ouvertes avec leur délai, état des équipements |
| Analyste | Catalogue des indicateurs et leur calculabilité, exploration, extractions |
| Producteur | Ses propres transmissions, les anomalies à corriger, les indicateurs qu'il alimente |
| Collectivité | Les données de son territoire, signalement, campagnes de collecte ouvertes |
| Administrateur | Comptes et habilitations, classification déléguée, journal d'accès |

Ces vues démontrent trois règles du Livrable 2 : un producteur ne voit que ses propres données, l'administrateur applique la classification sans la décider, et toute consultation de donnée non publique est journalisée.

Un bandeau en bas à gauche permet de passer du portail à l'application de collecte.

## Mise en ligne sur GitHub Pages

1. Créer un dépôt, par exemple `ontu-bf-maquettes`.
2. Y déposer le contenu de ce dossier à la racine, en conservant le fichier `.nojekyll`.
3. Dans les réglages du dépôt, ouvrir **Settings → Pages**.
4. Sous **Source**, choisir **Deploy from a branch**, puis la branche `main` et le dossier `/ (root)`.
5. Enregistrer. L'adresse publiée apparaît après une à deux minutes.

Le fichier `.nojekyll` est nécessaire : sans lui, GitHub applique un traitement qui ignore certains fichiers.

### En ligne de commande

```bash
git init
git add .
git commit -m "Maquettes ONTU-BF"
git branch -M main
git remote add origin https://github.com/VOTRE-COMPTE/ontu-bf-maquettes.git
git push -u origin main
```

Puis activer Pages dans les réglages du dépôt.

## Consultation hors ligne

Les deux fichiers s'ouvrent directement dans un navigateur, sans serveur. Deux réserves : la carte du portail et les polices de caractères sont chargées depuis Internet. Sans connexion, la mise en page reste correcte mais la carte ne s'affiche pas.

Pour une démonstration en salle sans connexion fiable, ouvrir les pages une première fois avec Internet afin que le navigateur mette les ressources en cache.

## Remplacer les illustrations par des photographies

Les trois vues du bandeau d'accueil sont des illustrations vectorielles, en attendant les photographies. Chacune est précédée d'un commentaire indiquant le fichier attendu :

| Vue | Fichier attendu | Sujet |
|---|---|---|
| 1 | `img/hero-echangeur.jpg` | Un échangeur de Ouagadougou, de préférence en fin de journée |
| 2 | `img/hero-rondpoint.jpg` | Un rond-point vu du ciel ou en plongée, avec la circulation |
| 3 | `img/hero-corridor.jpg` | Un corridor routier interurbain ou un chantier d'autoroute |

Pour substituer une photographie, remplacer le bloc `<svg>...</svg>` de la vue concernée par :

```html
<img src="img/hero-echangeur.jpg" alt="Échangeur de l'Est, Ouagadougou">
```

Format recommandé : 2400 pixels de large, cadrage horizontal, sujet décalé vers la droite. Le voile sombre couvre la moitié gauche, où se place le titre.

Vérifier les droits d'usage avant publication. Une photographie prise par l'équipe ou fournie par le maître d'ouvrage est préférable à une banque d'images.

## Ce que la maquette demande à l'équipe de réalisation

Les éléments suivants sont figurés mais non fonctionnels. Ils constituent la commande :

- le diaporama d'accueil, alimenté depuis le gestionnaire de contenu ;
- les anneaux de progression et les graphiques, alimentés depuis l'interface publique de la plateforme et non saisis en dur ;
- la carte, alimentée depuis les services géographiques ;
- le tableau des données ouvertes, alimenté depuis le catalogue ;
- les vues par profil, sélectionnables ici par le menu de démonstration.

## Ressources externes utilisées

- Leaflet, bibliothèque cartographique sous licence libre
- Fonds cartographique OpenStreetMap
- Polices Archivo, Inter et JetBrains Mono

Ces dépendances existent parce qu'il s'agit d'une maquette. Le site réel de l'Observatoire hébergera ces ressources localement, conformément au principe de non-dépendance à un service externe posé au Livrable 2.

## Ce que ces maquettes ne sont pas

Elles ne préfigurent ni la charte graphique définitive, ni l'arborescence retenue, ni le choix du gestionnaire de contenu. Le Livrable 2 pose la séparation entre le site éditorial et la plateforme de données, ainsi que les critères de choix du gestionnaire de contenu ; il ne désigne aucun produit.

## Licence et propriété

Ces maquettes sont produites pour le compte du maître d'ouvrage dans le cadre de la mission. Leur diffusion publique relève de sa décision.
