# Outil de visualisation des parcours biographiques

Outil de modélisation et d'export de trajectoires biographiques multi-dimensionnelles, conçu pour la recherche en sociologie sur les jeunes exilé·es. Il permet de saisir les données d'un ou plusieurs enquêtés, de les visualiser sous forme de frise chronologique en flèche, et d'exporter les résultats en SVG ou PNG.

---

## Prise en main rapide

1. **Ouvrir** le fichier `parcours_biographiques.html` dans votre navigateur (Chrome, Firefox ou Safari). Aucune installation requise.
2. L'outil s'ouvre avec un exemple préchargé (Maria, Angola, Rennes) pour illustrer le rendu.
3. **Ajouter un·e enquêté·e** via le bouton `+ Ajouter` dans le panneau gauche.
4. **Saisir les données** dans le panneau central, onglet par onglet.
5. **Exporter** la frise via les boutons `Exporter SVG` ou `Exporter PNG`.
6. **Sauvegarder** son travail via `💾 Sauvegarder JSON` en bas du panneau gauche.

> **Connexion internet requise au premier lancement** (chargement des bibliothèques React). Ensuite, l'outil fonctionne hors connexion.

---

## Interface

L'interface est divisée en trois panneaux.

### Panneau gauche — Liste des enquêté·es

Affiche l'ensemble des profils saisis. Un clic sur un nom le sélectionne et charge ses données dans le formulaire central. Le bouton `+ Ajouter` crée un nouveau profil vierge.

En bas du panneau :
- `💾 Sauvegarder JSON` — exporte l'ensemble des profils dans un fichier `.json` à conserver sur votre ordinateur.
- `📂 Charger JSON` — recharge un fichier `.json` précédemment sauvegardé pour reprendre le travail.

### Panneau central — Formulaire de saisie

Organisé en neuf onglets :

| Onglet | Contenu |
|--------|---------|
| **Général** | Prénom/code, pays d'origine, ville, âge au départ et à l'entretien |
| **Scol.** | Trajectoire scolaire |
| **Pro.** | Trajectoire professionnelle |
| **Résid.** | Trajectoire résidentielle |
| **Admin.** | Trajectoire administrative |
| **Relat.** | Trajectoire relationnelle |
| **Évén.** | Événements clés (repérés par des marqueurs sous la flèche) |
| **Phases** | Phases biographiques (labels en italique au-dessus de la flèche) |

### Panneau droit — Visualisation

Affiche la frise en temps réel à chaque modification. Contient également une légende dépliable de toutes les catégories de statut avec leurs couleurs.

---

## Saisir les données

### Informations générales

| Champ | Explication |
|-------|-------------|
| Prénom / Code | Identifiant de l'enquêté·e (prénom, pseudonyme ou code anonyme) |
| Pays d'origine | S'affiche dans l'en-tête de la frise |
| Ville | Ville d'enquête (ex. Rennes, Cork) |
| Âge au départ du pays d'origine | Marque une ligne pointillée rouge sur la frise |
| Âge à l'entretien | Définit la longueur totale de l'axe temporel |

### Trajectoires — Segments

Chaque trajectoire (scolaire, professionnelle, etc.) est composée de **segments** : des périodes délimitées par un âge de début et un âge de fin, associées à un statut et à une étiquette optionnelle.

Pour chaque segment :

- **De / À** : âges de début et de fin de la période
- **Statut** : catégorie parmi celles proposées dans le menu déroulant (voir listes complètes ci-dessous)
- **Étiquette** : texte court qui s'affiche dans le segment si l'espace le permet (ex. `École Angola`, `CADA Rennes`)

Un même enquêté peut avoir autant de segments que nécessaire par trajectoire. Les segments peuvent se succéder ou se chevaucher.

### Événements clés

Un événement est positionné à un âge donné sur l'axe et s'affiche sous la flèche. Champs :

- **Âge** : position sur l'axe
- **Libellé** : texte court (ex. `Arrivée en France`, `Refus OFPRA`)
- **Type** : détermine la couleur du marqueur

### Phases biographiques

Les phases apparaissent en italique entre guillemets au-dessus de la flèche, avec une accolade délimitant leur étendue temporelle. Elles permettent de nommer des périodes globales de la biographie (ex. `Angola · Enfance`, `France — Rennes`, `Transit`).

---

## Catégories de statut

### Trajectoire scolaire

| Statut | Couleur |
|--------|---------|
| Scolarisé·e | Bleu |
| Interrompu | Orange |
| Reprend études | Vert |
| Formation professionnelle | Violet |
| Université / Supérieur | Bleu foncé |
| Non scolarisé·e | Gris |

### Trajectoire professionnelle

| Statut | Couleur |
|--------|---------|
| Sans emploi | Gris |
| Emploi stable | Bleu foncé |
| Emploi précaire | Bleu |
| Bénévolat / Stage | Vert clair |
| Commerce / informel | Orange |
| Apprentissage | Vert |

### Trajectoire résidentielle

| Statut | Couleur |
|--------|---------|
| Famille (pays origine) | Vert |
| En transit | Orange |
| CADA / CHRS / DAHI | Bleu |
| Hébergé·e (tiers) | Bleu clair |
| 115 / Urgence / Rue | Rouge |
| Logement autonome | Bleu foncé |
| Colocation | Violet |

### Trajectoire administrative

| Statut | Couleur |
|--------|---------|
| Hors territoire | Gris clair |
| Sans statut | Rouge |
| Demandeur·euse d'asile | Orange |
| Débouté·e | Rouge vif |
| Procédure Dublin | Saumon |
| Prot. subsidiaire | Bleu clair |
| Réfugié·e statutaire | Bleu |
| TS étudiant·e | Violet |
| TS travailleur·euse | Vert |
| Citoyen·ne / naturalisé·e | Bleu foncé |

### Trajectoire relationnelle

| Statut | Couleur |
|--------|---------|
| Famille (pays origine) | Vert |
| Famille séparée | Gris |
| En couple | Violet |
| Parent | Orange |
| Seul·e | Saumon |
| Réseau social local | Vert clair |

### Types d'événements

| Type | Couleur |
|------|---------|
| Migration / Départ | Rouge |
| Événement admin. | Orange |
| Événement scolaire | Bleu |
| Événement relationnel | Violet |
| Événement professionnel | Vert |
| Moment clé | Gris foncé |

---

## Exporter les frises

### Format SVG (recommandé)

Le SVG est un format vectoriel : il peut être agrandi sans perte de qualité, et reste modifiable dans des logiciels comme **Inkscape** (gratuit) ou **Adobe Illustrator**. C'est le format recommandé pour intégrer les frises dans une thèse ou un article.

Après export, vous pouvez dans Inkscape :
- Modifier les couleurs, les tailles de texte, l'épaisseur des traits
- Déplacer ou supprimer des éléments
- Redimensionner la frise sans perte de qualité

### Format PNG

Le PNG est une image haute résolution (exportée en ×2 pour l'impression). Il est directement utilisable dans Word, PowerPoint, ou tout traitement de texte. Il ne peut pas être modifié dans un logiciel graphique après coup.

---

## Sauvegarder et reprendre le travail

L'outil ne conserve pas les données entre deux sessions : à la fermeture du navigateur, les profils saisis sont perdus **sauf si vous avez sauvegardé**.

**Workflow recommandé :**
1. En fin de session, cliquer sur `💾 Sauvegarder JSON`.
2. Conserver le fichier `parcours_biographiques.json` dans un dossier.
3. À la session suivante, ouvrir l'outil puis `📂 Charger JSON` pour retrouver tous les profils.

Le fichier JSON contient l'intégralité des données saisies (tous les enquêtés, tous les segments, événements et phases). Il peut être partagé avec un collègue qui utilise le même outil.

---

## Personnaliser l'outil

Le fichier HTML est un fichier texte standard. Il peut être ouvert et modifié dans n'importe quel éditeur de texte (Notepad++, Visual Studio Code, etc.) par une personne ayant des notions de JavaScript.

Les principales constantes modifiables se trouvent en début de script :

- **`STATUTS`** : les listes de statuts proposés dans chaque trajectoire
- **`COULEURS`** : les couleurs associées à chaque statut (codes hexadécimaux)
- **`TYPES_EVT`** et **`COULEURS_EVT`** : les types d'événements et leurs couleurs
- **`TRAJ_TYPES`** : les cinq trajectoires affichées (ordre et noms)

---

## Informations techniques

- **Technologies** : HTML / JavaScript (React 18, chargé depuis CDN)
- **Compatibilité** : Chrome 90+, Firefox 90+, Safari 14+
- **Données** : tout reste en local, aucune donnée n'est envoyée à un serveur
- **Connexion internet** : nécessaire au premier lancement uniquement (chargement de React depuis cdnjs.cloudflare.com)
- **Taille du fichier** : ~30 ko

---

## Crédits

Outil développé dans le cadre d'une thèse de doctorat en sociologie et science politique par Guillaume NEGRI (UMR 6051 Arènes, Université Rennes 2), portant sur les trajectoires biographiques des jeunes exilé·es à Rennes et Cork. Le modèle de visualisation s'inspire des frises biographiques développées dans les travaux de recherche en sociologie de la jeunesse et des parcours de vie.
