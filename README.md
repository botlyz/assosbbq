# Assos BBQ

Site web d'une association étudiante organisant des événements.

## Identification de l'équipe

| Pseudonyme GitHub | Nom | Prénom | Rôle |
|---|---|---|---|
| @botlyz | EL YADINI | Sofien | Étudiant 1 |
| @maelkobura | Butor-Blamont | Maël | Étudiant 2 |
| @LucasDevrin-code | Devrin | Lucas | Étudiant 3 |

## Fonctionnalités

- Présentation de l'association et navigation entre les sections.
- Catalogue de 3 événements avec un lien vers l'inscription.
- Formulaire d'inscription sans backend ni stockage.
- Identité visuelle et adaptation mobile.

## Responsabilités

| Étudiant | Responsabilités |
|---|---|
| Sofien EL YADINI | Présentation, navigation, identité visuelle, hotfix `v1.0.1` |
| Maël Butor-Blamont | Catalogue d'événements, adaptation mobile, résolution du conflit, release `v1.0` |
| Lucas Devrin | Formulaire d'inscription, coordination du conflit, correction du débordement |

## Étapes du développement

1. Création du dépôt, des branches `main` et `develop`, et de leurs protections.
2. Planification dans le GitHub Project avec les Issues et la Roadmap.
3. Développement des 3 fonctionnalités par Pull Request.
4. Évolutions parallèles et résolution d'un conflit Git.
5. Correction du débordement dans une branche `bugfix`.
6. Publication de `v1.0`, puis correction de l'incident dans `v1.0.1`.

## Workflow

Nous utilisons Git Flow :

- `main` contient les versions stables.
- `develop` contient le développement en cours.
- `feature/*`, `bugfix/*` et `docs/*` partent de `develop` et y reviennent par Pull Request.
- `release/*` prépare une version.
- `hotfix/*` part de `main` pour corriger la production, puis la correction est reportée sur `develop`.

Chaque Pull Request nécessite 2 approbations.

Limitation : au démarrage, un push direct sur `main` et la PR #1 sans revue ont eu lieu avant l'activation effective des protections. La PR #1 a servi à resynchroniser `develop`.

## Conflit et résolution

Les branches `feature/identite-visuelle` et `feature/adaptation-mobile` ont modifié le même bloc `nav` de `style.css`.

La première ajoutait une couleur de fond et un padding. La seconde ajoutait le retour à la ligne du menu et une taille de texte adaptée au mobile. Les valeurs de `gap` étaient différentes, ce qui a provoqué un vrai conflit après la fusion de la PR #14.

Lucas a coordonné l'intégration : la PR #14 a été fusionnée en premier, puis Maël a fusionné `develop` dans sa branche pour résoudre le conflit. Les deux améliorations ont été conservées, avec un `gap` de 8px adapté au mobile.

## Versions publiées

- `v1.0` : première version stable du site.
- `v1.0.1` : correction du lien de navigation vers les événements.

## Difficultés rencontrées

- Le débordement des cartes et le lien cassé vers les événements sont des anomalies simulées volontairement pour les exercices du sujet.
- Un push direct sur `main` a nécessité une PR de synchronisation vers `develop`.
- Plusieurs branches locales partaient d'un ancien historique et ont dû être réalignées sur `develop`.
- Une identité Git mal configurée a dû être corrigée pour rattacher les commits au bon compte.

## Questions de synthèse

### 1. Quel est l'intérêt de séparer développements en cours et versions stables ?

**Auteur : Maël Butor-Blamont**

Cette séparation permet de développer sans casser la version livrée. `main` reste stable, tandis que `develop` accueille les nouveautés avant leur validation.

### 2. Pourquoi imposer une revue de code avant intégration ?

**Auteur : Maël Butor-Blamont**

La revue permet de détecter les erreurs avant l'intégration, de vérifier le respect des critères et de partager la connaissance du code dans l'équipe.

### 3. Quelles situations provoquent un conflit Git et pourquoi sa résolution n'est-elle pas toujours automatique ?

**Auteur : Sofien EL YADINI**

Un conflit survient lorsque deux branches modifient les mêmes lignes d'un fichier. Git ne peut pas décider seul quelle version garder, car ce choix dépend de l'intention des développeurs.

### 4. Quelle différence entre correction classique et correction urgente de production ?

**Auteur : Sofien EL YADINI**

Une correction classique part de `develop` et sera livrée dans une prochaine version. Une correction urgente part de `main` pour réparer immédiatement la production, sans intégrer les développements en cours.

### 5. Pourquoi répercuter une correction de production dans les développements en cours ?

**Auteur : Sofien EL YADINI**

Sans ce report, `develop` garderait le bug, qui réapparaîtrait à la prochaine version. Le report garantit que la correction reste présente dans les versions futures.

### 6. Quel est le rôle d'une branche de release ?

**Auteur : Maël Butor-Blamont**

Elle prépare une version stable. On y fait les dernières vérifications et corrections, sans nouvelle fonctionnalité, avant de l'intégrer à `main` puis de reporter les corrections sur `develop`.

### 7. Comment GitHub Projects et les Issues facilitent-ils organisation et traçabilité ?

**Auteur : Lucas Devrin**

Les Issues décrivent chaque tâche, son responsable et ses critères. Le Project montre leur avancement et leur ordre. Les liens entre Issues, commits et Pull Requests permettent de suivre chaque changement.

### 8. Comment retrouver l'origine d'une modification dans l'historique GitHub ?

**Auteur : Lucas Devrin**

On consulte l'historique des commits ou la vue Blame d'un fichier. Le commit indique l'auteur, la date et le message, et son numéro d'Issue ou sa Pull Request donne le contexte de la modification.