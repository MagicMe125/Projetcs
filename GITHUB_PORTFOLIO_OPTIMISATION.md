# Optimisation du portfolio GitHub de Jacques Tsiorimalala

Ce document transforme les recommandations de l’échange en plan d’exécution concret. Le nouveau contenu proposé est déjà appliqué dans le fichier [`README.md`](./README.md) placé à côté de ce guide.

## Objectif

Permettre à un prospect arrivant depuis LinkedIn, un e-mail ou une candidature de comprendre en **20 à 30 secondes** :

1. qui est Jacques Tsiorimalala ;
2. quels problèmes il peut résoudre ;
3. quelles réalisations prouvent son expérience ;
4. qu’il est disponible en freelance et en sous-traitance ;
5. comment le contacter immédiatement.

Le dépôt ne doit plus être seulement une liste de projets. Il doit fonctionner comme une page commerciale courte, puis donner accès aux études de cas détaillées.

## Ordre de priorité

### 1. Corriger le nom du dépôt

Nom recommandé : **`portfolio`**.

Alternative si ce nom n’est pas souhaité : **`Projects`**.

Éviter de conserver `Projetcs`, dont la faute de frappe peut donner une impression de négligence avant même la lecture du contenu.

Cette opération doit être effectuée manuellement sur GitHub lorsque le nouveau README aura été vérifié :

1. ouvrir le dépôt sur GitHub ;
2. aller dans **Settings** ;
3. modifier **Repository name** ;
4. choisir `portfolio` ;
5. valider le renommage ;
6. mettre à jour l’adresse du dépôt local si nécessaire :

```bash
git remote set-url origin https://github.com/MagicMe125/portfolio.git
```

GitHub redirige généralement l’ancienne URL, mais il faut tout de même remplacer progressivement les anciens liens dans les profils, candidatures et messages.

> Le renommage distant n’a pas été effectué automatiquement par ce travail.

### 2. Transformer les 20 premières secondes de lecture

Le haut du README doit contenir, dans cet ordre :

1. le nom ;
2. le positionnement : full-stack, WordPress et SEO technique ;
3. les types de produits réalisés : SaaS, applications métier et WordPress ;
4. la disponibilité pour des missions freelance, du renfort et de la sous-traitance ;
5. un CTA e-mail visible ;
6. les trois projets phares.

Les longs blocs sur les compétences, WordPress, le parcours et l’IA restent utiles, mais viennent après les preuves.

### 3. Mettre les preuves dans le bon ordre

Ordre retenu dans le nouveau README :

1. **Didaxo** — meilleure preuve pour une mission SaaS, React/Node ou outil métier ;
2. **EasyPartner** — preuve WordPress, HubSpot, migration, recrutement et continuité SEO ;
3. **Architoi** — preuve d’intégration WordPress en marque blanche avec expérience interactive.

Chaque projet phare répond immédiatement à trois questions :

- qu’est-ce qui a été construit ?
- avec quelles technologies ?
- qu’est-ce que cette réalisation prouve pour un prospect ?

### 4. Conserver les compétences et les autres projets

Les autres réalisations restent présentes après les projets phares : Braise, CRM, FACT, iDigital Revolution, Blogs WordPress, Tah Voyage Madagascar et Light Genius.

Elles renforcent la profondeur du profil sans ralentir la première lecture.

## Liens directs à utiliser selon la mission

Après renommage du dépôt en `portfolio`, utiliser le lien le plus proche du besoin au lieu d’envoyer uniquement la racine du dépôt.

### React, Node.js, SaaS, MVP ou application métier

Lien principal :

```text
https://github.com/MagicMe125/portfolio/tree/main/Didaxo
```

Preuves complémentaires : FACT, CRM et Braise.

Exemple de formulation :

> Vous recherchez un développeur pour un SaaS React/Node. J’ai notamment développé Didaxo, une plateforme métier avec React, Node.js, MySQL, Stripe et automatisation documentaire : https://github.com/MagicMe125/portfolio/tree/main/Didaxo
>
> Portfolio complet : https://github.com/MagicMe125/portfolio

### WordPress, refonte, plugin ou sous-traitance en marque blanche

Lien principal pour une refonte et une intégration CRM :

```text
https://github.com/MagicMe125/portfolio/tree/main/EasyPartner
```

Lien principal pour une intégration en marque blanche :

```text
https://github.com/MagicMe125/portfolio/tree/main/Architoi
```

Preuves complémentaires : Light Genius et Blogs WordPress.

### SEO technique associé au développement

Selon la demande :

```text
https://github.com/MagicMe125/portfolio/tree/main/CRM
https://github.com/MagicMe125/portfolio/tree/main/EasyPartner
https://github.com/MagicMe125/portfolio/tree/main/TahvoyageMadagascar
```

### Automatisation, API, CRM ou intégrations externes

Selon la demande :

```text
https://github.com/MagicMe125/portfolio/tree/main/Didaxo
https://github.com/MagicMe125/portfolio/tree/main/EasyPartner
https://github.com/MagicMe125/portfolio/tree/main/CRM
```

> Si le dépôt est finalement renommé `Projects`, remplacer simplement `/portfolio/` par `/Projects/` dans tous ces exemples.

## Structure complète retenue pour le README

Le fichier [`README.md`](./README.md) contient la version complète, prête à publier, structurée ainsi :

1. **Nom et positionnement** ;
2. **disponibilité freelance / sous-traitance** ;
3. **technologies et domaines clés** ;
4. **CTA vers les réalisations, le portfolio et l’e-mail** ;
5. **Didaxo, EasyPartner et Architoi** ;
6. **table d’orientation par type de mission** ;
7. **prestations pouvant être prises en charge** ;
8. **compétences techniques** ;
9. **autres réalisations** ;
10. **méthode de travail** ;
11. **usage maîtrisé de l’IA** ;
12. **parcours** ;
13. **CTA de contact final** ;
14. **mention sur la confidentialité du code propriétaire**.

Le contenu utilise uniquement les informations déjà présentes dans le portfolio et dans l’échange : aucun chiffre, client, résultat commercial ou compétence supplémentaire n’a été inventé.

## Petit dépôt public de démonstration — option recommandée

Les études de cas montrent **ce que Jacques sait construire**. Un petit dépôt public montrerait **comment il code** sans exposer Didaxo, Braise ou un autre produit propriétaire.

### Périmètre conseillé

Créer une application volontairement réduite, par exemple un mini outil de suivi de demandes ou de projets, avec :

- une interface React et TypeScript ;
- une API Node.js / Express ;
- une base PostgreSQL ou MySQL ;
- authentification et contrôle d’accès simples ;
- validation des entrées et gestion claire des erreurs ;
- quelques tests utiles ;
- configuration Docker ;
- jeu de données de démonstration sans donnée réelle ;
- README expliquant l’architecture, les choix, l’installation et les limites ;
- historique Git propre et commits compréhensibles.

Le but n’est pas de construire un nouveau produit complexe. Une petite base très soignée est plus convaincante qu’une grosse démonstration inachevée.

### À ne jamais publier

- code copié depuis un projet client ou propriétaire ;
- clés API, secrets, mots de passe ou fichiers d’environnement ;
- données réelles ;
- noms internes, documents ou captures confidentiels ;
- composants dont les droits de publication ne sont pas clairement établis.

## Checklist d’exécution dans Visual Studio Code

### README principal

- [x] Placer le positionnement full-stack, WordPress et SEO technique en haut.
- [x] Indiquer la disponibilité freelance, renfort d’équipe et sous-traitance.
- [x] Afficher immédiatement le CTA e-mail.
- [x] Faire remonter Didaxo en première position.
- [x] Présenter EasyPartner en deuxième position.
- [x] Présenter Architoi en troisième position.
- [x] Ajouter une table d’orientation par type de mission.
- [x] Conserver les compétences après les preuves.
- [x] Conserver les autres projets dans une section dédiée.
- [x] Expliquer pourquoi le code des projets commerciaux n’est pas public.
- [x] Vérifier les chemins relatifs vers chaque dossier.

### Contrôle visuel et éditorial

- [ ] Ouvrir l’aperçu Markdown dans Visual Studio Code.
- [ ] Vérifier que les trois projets phares apparaissent sans longue lecture préalable.
- [ ] Cliquer sur chaque lien relatif vers une étude de cas.
- [ ] Cliquer sur les deux liens `mailto:`.
- [ ] Vérifier le lien vers `jacques.idigital-revolution.com`.
- [ ] Relire la version mobile sur GitHub après publication.
- [ ] Vérifier qu’aucune information confidentielle n’a été ajoutée.

### Publication

- [ ] Examiner les changements avec le contrôle de source de Visual Studio Code.
- [ ] Créer un commit consacré à l’optimisation du portfolio.
- [ ] Envoyer le commit sur GitHub.
- [ ] Renommer `Projetcs` en `portfolio` dans les paramètres GitHub.
- [ ] Mettre à jour l’URL `origin` locale après le renommage.
- [ ] Mettre à jour le lien GitHub sur le portfolio personnel.
- [ ] Mettre à jour les liens utilisés sur LinkedIn et dans les modèles de candidature.
- [ ] Tester les liens directs Didaxo, EasyPartner, Architoi, CRM, FACT et Braise.

### Dépôt public de démonstration

- [ ] Choisir un périmètre réalisable et indépendant des projets propriétaires.
- [ ] Créer un dépôt public séparé.
- [ ] Ajouter tests, Docker, documentation et données fictives.
- [ ] Effectuer une vérification complète des secrets avant publication.
- [ ] Ajouter le lien au README principal uniquement lorsque le dépôt est propre et terminé.

## Critère final de réussite

Une personne ne connaissant pas Jacques doit pouvoir répondre en moins de 30 secondes :

- **Profil :** développeur full-stack, WordPress et SEO technique ;
- **offre :** SaaS, outils métier, WordPress, API, automatisations et sous-traitance ;
- **preuves :** Didaxo, EasyPartner et Architoi ;
- **contact :** jacques@idigital-revolution.com.

Si ces quatre réponses sont visibles sans effort, le README remplit sa fonction de conversion.
