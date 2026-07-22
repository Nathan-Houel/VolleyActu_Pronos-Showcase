🇫🇷 **Français** | 🇬🇧 [English](README.en.md)

![VolleyActu_banner](assets/screenshots/VolleyActu_banner.png)

# VolleyActu_Pronos

> ⚠️ **Code source non disponible publiquement.**
> Ce projet est utilisé activement par [VolleyActu](https://www.volleyactu.fr). Le code source reste privé, mais ce dépôt documente l'architecture, les fonctionnalités et les choix techniques du projet VolleyActu_Pronos disponible dans la section Prédictions du site.

---

## 📌 Présentation

**VolleyActu_Pronos** est un plugin *Wordpress* développé pour **VolleyActu**. Ce plugin permet aux fans de volley-ball de soumettre leurs pronostics pendant les compétitions de Ligue des nations masculine et féminine, de s'affronter grâce à un système de score dynamique, et de suivre leur classement en temps réel.

L'objectif est d'offrir à la communauté de VolleyActu un moyen engageant de suivre la compétition au-delà de la simple lecture d'articles, en transformant des lecteurs passifs en participants actifs.

## 🎯 Le besoin

Auparavant, les membres de la communauté VolleyActu réalisaient leurs pronostics chacun de leur côté à l'aide de tableur, faute de plateforme dédiée et gratuite
Afin de fédérer davantage cette communauté, VolleyActu a donc eu pour objectif de lancer un système de prédiction inspiré du système de [LaSource.gg](https://lasource.gg/predictions). 

L'objectif principal était de déployer ce système pour l'été 2026 afin de pouvoir couvrir la Ligue des Nations masculine et féminine ainsi que le Championnat d'Europe 2026. À l'issue de mes échanges avec l'équipe de VolleyActu, je me suis engagé à développer ce système de prédictions entre la fin mars et la mi-mai.

## 👤 Mon rôle

Mon rôle a été de développer entièrement le plugin à partir de zéro. Pour ce faire, je suis parti d'une installation WordPress vierge à laquelle j'ai intégré chaque fonctionnalité de manière incrémentale. J'ai organisé des points réguliers avec les responsables de VolleyActu afin de valider les fonctionnalités développées et d'identifier les axes d'amélioration.

Voici une liste des principales fonctionnalités de ce plugin:
- Conception de la logique de pronostics et de scoring
- Développement du plugin WordPress (PHP / JavaScript) à partir de zéro
- Implémentation de l'authentification Google OAuth
- Conception d'une page Profil
- Conception du modèle de données MySQL
- Développement de l'interface d'administration pour la gestion des matchs
- Déploiement et maintenance du plugin en production
- Automatisation du pipeline à l'aide de l'API-Sports

## 🏗️ Architecture

![Architecture](assets/architecture.png)

Le plugin s'intègre directement à l'installation WordPress existante de VolleyActu :

1. L'**utilisateur** soumet un pronostic via l'interface du plugin
2. **WordPress** affiche le plugin et gère le contexte de page/utilisateur
3. Le **plugin VolleyActu_Pronos** gère la logique métier : validation, règles de scoring, calcul du classement
4. **Google OAuth** authentifie les utilisateurs sans nécessiter la création d'un compte séparé
5. **MySQL** stocke les pronostics, les résultats des matchs et les scores des utilisateurs
6. Le **classement** est calculé et affiché en temps réel
7. L'**API-Sports** permet d'automatiser la validation et d'avoir en temps réel les scores des matchs.

Voici la structure du dossier du plugin :
```
├── 📁 admin
│   └── 🐘 admin-page.php
├── 📁 includes
│   ├── 🐘 class-config.php
│   ├── 🐘 class-database.php
│   ├── 🐘 class-hub.php
│   ├── 🐘 class-migrations.php
│   ├── 🐘 class-profil.php
│   └── 🐘 class-scores.php
├── 📁 public
│   ├── 📁 css
│   │   ├── 🎨 colors.css
│   │   ├── 🎨 hub.css
│   │   └── 🎨 profil.css
│   └── 📁 js
│       ├── 📄 hub.js
│       └── 📄 profil.js
├── 📁 templates
│   ├── 🐘 hub-view.php
│   └── 🐘 profil-view.php
└── 🐘 VA-pronos.php
```

## 🛠️ Stack technique

| Couche | Technologie |
|---|---|
| CMS | WordPress |
| Backend | PHP |
| Frontend | JavaScript |
| Base de données | MySQL |
| Authentification | Google OAuth |
| Automatisation | API-Sports |

## ✨ Fonctionnalités clés

- 🔐 **Authentification Google** : connexion en un clic, pas de système de compte séparé à gérer
- 📝 **Formulaire de pronostic** : les utilisateurs soumettent leurs pronostics avant chaque match
- 📊 **Système de score dynamique** : points attribués selon la précision des pronostics
- 🏆 **Classement en temps réel** : mis à jour automatiquement à mesure que les résultats arrivent
- 🛠️ **Panel d'administration** : gestion des matchs, saisie des résultats, supervision de la compétition

## 📊 Résultats & impact

- **220** matchs gérés depuis le *22 juillet 2026*
- **36 000** pronostics soumis
- **541** utilisateurs actifs
- En production et maintenu activement depuis **28 mai 2026**

## 📸 Captures d'écran

| Page d'accueil prédictions | Résultats des matchs |
|---|---|
| ![Page d'accueil prédictions](assets/screenshots/VA-pronos.png) | ![Résultats des matchs](assets/screenshots/VA-results.png) |

| Profil | Classement Général |
|---|---|
| ![Profil](assets/screenshots/Profil.png) | ![Classement Général](assets/screenshots/Profil-leaderboard.png) |

| Statistiques de l'utilisateur | Création des matchs - Admin |
|---|---|
| ![Statistiques de l'utilisateur](assets/screenshots/Profil-statistics.png) | ![Création des matchs - Admin](assets/screenshots/Admin_matchs.png) |

## 🔮 Avenir du projet

L'ambition à moyen terme est d'étendre les fonctionnalités du plugin pour couvrir les championnats de clubs (masculins et féminins).

Les ligues ciblées en priorité sont :
- 🇫🇷 La France
- 🇮🇹 L'Italie
- 🇵🇱 La Pologne

Le déploiement de ces nouvelles compétitions dépendra des retours de la communauté et du taux de rétention des utilisateurs actuels.

## 🔒 Pourquoi le code n'est-il pas public ?

Le plugin est actuellement déployé et utilisé par VolleyActu. Pour protéger le projet et ses utilisateurs, le code source reste privé. Ce dépôt se concentre sur la documentation de l'architecture et des choix d'ingénierie derrière le produit.

## 📄 Licence

Cette documentation est partagée sous licence [MIT](LICENSE). Le code source n'est pas inclus.


## 👨‍💻 Auteur

Houel Nathan - *Juillet 2026*