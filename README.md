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

## Versions publiées

## Difficultés rencontrées

## Questions de synthèse

### 3. Quelles situations provoquent un conflit Git et pourquoi sa résolution n'est-elle pas toujours automatique ?

**Auteur : Sofien EL YADINI**

Un conflit survient lorsque deux branches modifient les mêmes lignes d'un fichier. Git ne peut pas décider seul quelle version garder, car ce choix dépend de l'intention des développeurs.

### 4. Quelle différence entre correction classique et correction urgente de production ?

**Auteur : Sofien EL YADINI**

Une correction classique part de `develop` et sera livrée dans une prochaine version. Une correction urgente part de `main` pour réparer immédiatement la production, sans intégrer les développements en cours.

### 5. Pourquoi répercuter une correction de production dans les développements en cours ?

**Auteur : Sofien EL YADINI**

Sans ce report, `develop` garderait le bug, qui réapparaîtrait à la prochaine version. Le report garantit que la correction reste présente dans les versions futures.