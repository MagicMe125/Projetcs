# FACT

**Fully Automated Compliance & Transmission** — SaaS de facturation destiné aux TPE, PME et indépendants, conçu pour réunir clients, devis, factures, paiements et pilotage de trésorerie dans une interface unique.

> Projet en développement — le code source est conservé dans un dépôt privé.

## Le projet

FACT répond à un double besoin : simplifier la gestion commerciale quotidienne et préparer les entreprises à la facturation électronique structurée.

L’application couvre le parcours complet, de la création d’un client jusqu’au suivi de l’encaissement. Les règles métier sensibles — numérotation, verrouillage des documents finalisés, création d’avoirs et cloisonnement par entreprise — sont prises en charge par le backend afin de garantir un comportement cohérent quel que soit l’écran utilisé.

## Fonctionnalités principales

### Tableau de bord

- chiffre d’affaires facturé sur la période ;
- comparaison avec la période précédente ;
- encours client et factures en retard ;
- échéancier des paiements à venir ;
- devis en attente de réponse ;
- délai moyen de paiement ;
- top clients et répartition du chiffre d’affaires ;
- suivi des statuts de transmission électronique.

### Gestion des clients

- fiches clients particuliers et professionnels ;
- identification automatique B2B ou B2C selon la présence d’un SIRET ;
- coordonnées, adresses et contacts ;
- régime de TVA et numéro intracommunautaire ;
- conditions de paiement et mode de règlement par défaut ;
- remise commerciale personnalisée ;
- informations liées à la réception électronique.

### Catalogue

- gestion des produits et services ;
- référence interne, désignation et description ;
- prix unitaire hors taxes ;
- taux de TVA et unité de facturation ;
- classement par catégorie ;
- réutilisation des éléments du catalogue dans les devis et factures.

### Devis

- création guidée avec lignes libres ou issues du catalogue ;
- calcul automatique des montants HT, TVA et TTC ;
- numérotation propre à chaque entreprise ;
- cycle de vie : brouillon, envoyé, accepté, refusé ou expiré ;
- historique des changements ;
- verrouillage après acceptation ;
- création d’une nouvelle révision liée au devis d’origine ;
- conversion en facture normale, acompte ou solde ;
- contrôle empêchant de facturer au-delà du montant accepté.

### Facturation

- création directe ou depuis un devis ;
- facture modifiable tant qu’elle reste en brouillon ;
- attribution du numéro définitif lors de la finalisation ;
- verrouillage du contenu fiscal et légal après finalisation ;
- notes internes toujours modifiables ;
- correction d’une facture finalisée exclusivement par un avoir lié ;
- historique complet des événements ;
- dates d’émission et d’échéance calculées selon les conditions du client.

### Préparation à la facturation électronique

- sélection d’une Plateforme Agréée par entreprise ;
- distinction entre transmission structurée B2B et envoi classique B2C ;
- suivi du statut de transmission ;
- gestion des erreurs, rejets et nouvelles tentatives ;
- conservation du lien entre devis, facture, avoir et paiement ;
- architecture préparée pour accueillir des connecteurs réels vers plusieurs plateformes.

### Paiements

- enregistrement des paiements par carte ou virement SEPA ;
- prise en charge des paiements partiels ;
- calcul des frais supportés par le payeur ;
- rapprochement automatique avec la facture ;
- passage de la facture au statut payé après encaissement complet ;
- historique des transactions par entreprise.

### Trésorerie

- solde et mouvements prévisionnels ;
- projection à 30, 60 et 90 jours ;
- prise en compte des factures, devis, charges et notes de frais ;
- alertes sur les échéances et niveaux de trésorerie ;
- fonctionnalité prévue pour le palier Premium.

### Export comptable

- export CSV des factures finalisées ;
- génération d’un Fichier des Écritures Comptables simplifié ;
- séparation des écritures client, vente et TVA ;
- données préparées pour faciliter la transmission à un expert-comptable.

### Comptes et accès

- inscription autonome avec création de la première entreprise ;
- validation obligatoire de l’adresse e-mail ;
- essai gratuit de quatre jours déclenché après validation ;
- connexion sécurisée avec mot de passe haché ;
- réinitialisation du mot de passe par jeton temporaire ;
- limitation des tentatives sur les routes sensibles ;
- suspension des fonctions métier après expiration de l’essai ;
- gestion de plusieurs entreprises depuis un même compte.

## Aperçu

### Tableau de bord financier

![Tableau de bord FACT](<tableau de bord.png>)

### Catalogue de produits et services

![Catalogue de produits et services](<catalogue de produits et services.png>)

### Création d’un devis

![Éditeur de devis](<création devis.png>)

### Document numérique

![Aperçu d’une facture numérique](<facture numérique.png>)

### Gestion et transmission des factures

![Détail d’une facture et suivi de transmission](<gestion facture.png>)

### Suivi des paiements

![Historique et suivi des paiements](<gestion paiements.png>)

## Architecture technique

| Couche | Technologies |
| --- | --- |
| Interface | Astro 7, TypeScript, rendu SSR |
| API | Node.js, Express, TypeScript |
| Validation | Zod |
| Accès aux données | Prisma ORM |
| Base de données | PostgreSQL |
| Authentification | JWT, bcrypt |
| E-mails | Nodemailer |
| Déploiement | Docker, Docker Compose, Nginx |

Le backend suit une organisation en couches :

1. les routes HTTP valident et transmettent les requêtes ;
2. les services portent les règles métier ;
3. les repositories isolent l’accès aux données ;
4. Prisma assure la persistance dans PostgreSQL.

Cette structure facilite l’évolution du produit et limite le couplage entre l’interface, les règles de facturation et la base de données.

## Multi-entreprises

Un utilisateur peut accéder à plusieurs structures juridiques depuis le même compte. Chaque requête métier est rattachée à une entreprise active et les données sont strictement filtrées par son identifiant.

Chaque entreprise conserve notamment :

- ses clients et son catalogue ;
- ses devis et factures ;
- sa propre séquence de numérotation ;
- ses transactions et données de trésorerie ;
- sa configuration de Plateforme Agréée ;
- son régime de TVA et ses informations légales.

## Règles métier importantes

- un devis accepté ne peut plus être modifié directement ;
- une révision crée un nouveau devis lié à l’original ;
- la somme des factures issues d’un devis ne peut pas dépasser son total ;
- une facture reste non numérotée tant qu’elle est en brouillon ;
- une facture finalisée devient immuable sur ses champs fiscaux ;
- toute correction passe par un avoir lié à la facture d’origine ;
- les documents et transactions sont toujours contrôlés dans le périmètre de l’entreprise active ;
- un essai expiré conserve les données mais bloque les opérations métier.

## Périmètre actuel

FACT est un prototype SaaS avancé. Les règles de facturation, l’authentification, la persistance PostgreSQL et les principaux parcours métier sont opérationnels.

Certaines intégrations sont encore simulées ou à finaliser avant une exploitation commerciale :

- connexion réelle à une ou plusieurs Plateformes Agréées ;
- production et validation complète du format Factur-X ;
- paiements Stripe ou Stripe Connect et webhooks associés ;
- signature électronique par un prestataire qualifié ;
- validation définitive de l’export FEC par un expert-comptable ;
- archivage légal à valeur probante.

## Points techniques travaillés

- traduction de contraintes comptables en règles applicatives ;
- immutabilité des documents après finalisation ;
- cohérence du cycle devis, facture, avoir et paiement ;
- architecture multi-tenant cloisonnée par entreprise ;
- modélisation relationnelle avec Prisma ;
- validation centralisée des entrées avec Zod ;
- gestion sécurisée des comptes et jetons temporaires ;
- stratégie de sauvegarde et de réinstallation PostgreSQL ;
- déploiement séparé du frontend SSR et de l’API.

## Accès au code

Le dépôt source est privé afin de protéger les règles métier, les configurations d’infrastructure et les futures intégrations de paiement et de transmission. Une présentation technique détaillée peut être proposée dans le cadre d’un recrutement ou d’une collaboration.

---

Conception et développement : **Jacques Tsiorimalala**
