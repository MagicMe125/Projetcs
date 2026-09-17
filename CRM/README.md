# CRM — Back-office & pilotage SEO

Interface d’administration sur mesure réunissant gestion de contenu, suivi éditorial et pilotage SEO du portfolio dans un seul outil.

> Le code source et l’accès à l’administration sont privés.

## Le projet

Ce CRM a été développé pour administrer un portfolio professionnel sans dépendre d’un CMS généraliste ni d’une accumulation de plugins. Il couvre à la fois la publication des contenus et l’analyse de leur visibilité dans Google.

L’objectif est de disposer d’un espace de travail unique pour rédiger, optimiser, publier et suivre les performances SEO des articles, études de cas et pages du site.

## Fonctionnalités principales

### Gestion éditoriale

- création et modification d’articles de blog et d’études de cas ;
- gestion des catégories éditoriales ;
- administration des pages statiques du site ;
- éditeur de contenu enrichi ;
- gestion des images à la une et des visuels Open Graph ;
- ajout de FAQ structurées ;
- suivi du statut de publication ;
- compteurs de caractères pour les champs sensibles au référencement.

### Optimisation SEO intégrée

- définition d’un mot-clé cible par contenu ;
- édition des balises `title` et des meta descriptions ;
- score SEO calculé à partir de critères pondérés ;
- recommandations actionnables pendant la rédaction ;
- analyse de la structure des titres, du contenu et des liens ;
- prévisualisation des données structurées JSON-LD ;
- prise en charge des schémas Article, FAQ, Person et Organization.

### Audit des pages publiées

- analyse de la page réellement disponible en production ;
- contrôle du statut HTTP, des balises et de l’URL canonique ;
- vérification des images et des métadonnées Open Graph ;
- comparaison entre les informations enregistrées et le rendu public ;
- audit individuel ou global des pages suivies ;
- synchronisation des pages depuis le sitemap XML.

### Suivi Search Console

- synchronisation des requêtes depuis l’API Google Search Console ;
- suivi des clics, impressions et positions moyennes ;
- historique de positionnement par mot-clé ;
- évolution des performances sur plusieurs périodes ;
- inspection de l’indexation des URL ;
- mise en cache des résultats pour respecter les quotas Google.

### Analyse concurrentielle

- suivi des concurrents présents dans les résultats organiques ;
- comparaison entre la position du site et celle du premier concurrent ;
- identification des pages concurrentes positionnées ;
- synchronisation automatisée des SERP via une API externe.

### Maillage interne

- exploration des liens présents sur le site public ;
- construction du graphe entre articles, catégories et pages ;
- détection des contenus orphelins ou insuffisamment liés ;
- conservation du dernier graphe valide en cas d’échec d’un scan ;
- suivi du nombre de pages explorées et des éventuelles erreurs.

### Tableau de bord

- synthèse des articles et catégories publiés ;
- nombre de mots-clés positionnés ;
- état de l’indexation des pages ;
- dernières publications ;
- tendances de visibilité ;
- intégration facultative des données de trafic Google Analytics 4.

### Utilisateurs et sécurité

- authentification par session serveur ;
- rôles administrateur et auteur ;
- invitation de nouveaux contributeurs par e-mail ;
- jetons temporaires et réinitialisation de mot de passe ;
- cookies de session `HttpOnly` et sécurisés en production ;
- restriction des routes d’administration aux utilisateurs authentifiés.

## Aperçu

### Tableau de bord

![Tableau de bord éditorial et SEO](<tableau de bord.png>)

### Pilotage des contenus

![Tableau des articles avec leur score SEO](<tableau articles.png>)

### Éditeur et recommandations SEO

![Édition d’un article et recommandations SEO](<audit edition article.png>)

### Audit des pages publiées

![Audit technique des pages publiées](<audit technique.png>)

### Suivi des pages

![Pages suivies et scores SEO](<tableau page.png>)

### Maillage interne

![Analyse du maillage interne](<audit maillage interne.png>)

### Positions des mots-clés

![Suivi des mots-clés depuis Search Console](<suivi mots clés.png>)

## Architecture technique

| Couche | Technologies |
| --- | --- |
| Interface d’administration | React 18, Vite, React Router |
| Design system | Tailwind CSS, Lucide React |
| Visualisation des données | Recharts |
| API | Node.js, Express |
| Base de données | MySQL, Knex.js |
| Site public piloté | Astro |
| Données SEO | Google Search Console, Google Analytics 4 |
| Analyse concurrentielle | API Serper |
| E-mails | Nodemailer |
| Déploiement | Docker, Nginx, Let’s Encrypt |

L’application est séparée en trois briques :

1. une interface React réservée à l’administration ;
2. une API REST Express qui gère le contenu, l’authentification et les analyses ;
3. un site Astro public qui consomme les contenus publiés.

Cette séparation permet de faire évoluer le CRM sans alourdir le site public et de conserver les performances d’une génération Astro orientée SEO.

## Choix techniques importants

- stockage en base des données Search Console afin de conserver un historique exploitable ;
- agrégation des positions par requête et par date, pondérée par les impressions ;
- cache des résultats d’inspection pour maîtriser les quotas d’API ;
- moteur de score partagé entre les contenus en base et les pages en production ;
- migrations de base de données versionnées avec Knex.js ;
- scans de maillage tolérants aux erreurs pour ne jamais remplacer un graphe valide par un résultat vide ;
- tâches planifiées pour actualiser les données SEO et l’état d’indexation.

## Pourquoi un outil sur mesure ?

Un CMS classique sait publier du contenu, tandis que les outils SEO externes savent mesurer sa performance. Ce CRM relie directement les deux usages : chaque contenu peut être rédigé, optimisé, audité et suivi dans la même interface.

Le projet évite ainsi de jongler entre un CMS, un plugin SEO, Search Console et plusieurs tableaux de suivi. Il transforme le back-office du portfolio en véritable outil de pilotage éditorial et technique.

## Résultat

Le CRM centralise tout le cycle de vie d’un contenu : préparation, optimisation, publication, indexation, positionnement et amélioration du maillage interne. Il constitue également une démonstration concrète d’une double expertise en développement full-stack et en SEO technique.

## Accès au code

Le dépôt source et l’interface d’administration restent privés afin de protéger les accès, les intégrations et les données analytiques. Une démonstration encadrée peut être proposée dans le cadre d’un recrutement ou d’une collaboration.

---

Conception et développement : **Jacques Tsiorimalala**
