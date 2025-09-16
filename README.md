# Template Site Web - Science Citoyenne

Template Jekyll pour documenter des actions de science citoyenne environnementale, basé sur le thème [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes).

## Vue d'ensemble

Ce template a été spécialement adapté pour l'activité **"Créer un site web pour documenter ses actions de science citoyenne grâce à GitHub Pages"** du programme JEDI-Track. Il présente l'exemple du groupe fictif "jedi-track" qui documente ses campagnes de surveillance environnementale.

## Structure du Site

Le template contient :

### Pages principales
- **Accueil** (`_pages/index.md`) : Présentation de l'équipe, mission environnementale et zone d'étude
- **Nos campagnes** (`_pages/campagnes.md`) : Documentation des relevés, méthodologie, données collectées
- **Impact local** (`_pages/impact.md`) : Problèmes identifiés, solutions proposées, actions auprès des décideurs
- **Rejoignez-nous** (`_pages/rejoignez-nous.md`) : Calendrier des formations, participation, contact

### Contenu d'exemple
- **4 articles de blog** illustrant différents aspects des campagnes de science citoyenne
- **Données environnementales réalistes** (qualité air/eau, biodiversité)
- **Exemples de partenariats** avec institutions scientifiques
- **Méthodologies de collecte** de données détaillées
- **Impact politique concret** (présentations en conseil municipal)

## Utilisation du Template

### 1. Configuration de base
Modifiez le fichier `_config.yml` :
- `title` : Nom de votre groupe
- `email` : Adresse de contact
- `description` : Description de votre mission
- `author.name` : Nom de votre équipe
- Réseaux sociaux et liens

### 2. Personnalisation du contenu
- **Remplacez "jedi-track"** par le nom de votre groupe dans tous les fichiers
- **Adaptez la zone d'étude** à votre contexte local
- **Modifiez les données d'exemple** avec vos vraies mesures
- **Ajustez les partenariats** selon vos collaborations

### 3. Navigation
La navigation est configurée dans `_data/navigation.yml` selon les besoins de la science citoyenne.

## Déploiement

### GitHub Pages (recommandé)
1. Forkez ce dépôt
2. Activez GitHub Pages dans les paramètres du dépôt
3. Personnalisez le contenu
4. Votre site sera accessible à l'adresse : `https://[votre-nom].github.io/[nom-du-depot]`

### Développement local
```bash
# Installer les dépendances
bundle install

# Lancer le serveur de développement
bundle exec jekyll serve

# Construire le site pour la production
bundle exec jekyll build
```

## Fonctionnalités Incluses

- **Présentation professionnelle** adaptée aux présentations en conseil municipal
- **Documentation scientifique** rigoureuse des protocoles
- **Engagement citoyen** avec calendrier des formations
- **Impact mesurable** sur les politiques locales
- **Référencement optimisé** (SEO)
- **Responsive design** pour tous les appareils
- **Flux RSS** pour les actualités
- **Recherche intégrée** dans le site

## À Propos de JEDI-Track

Ce template a été conçu dans le cadre des activités pédagogiques JEDI-Track pour accompagner les groupes de citoyens dans la documentation de leurs actions environnementales.

**Lien vers l'activité :** [Créer un site web pour documenter ses actions de science citoyenne grâce à GitHub Pages](https://jedi-track.notion.site/Cr-er-un-site-web-pour-documenter-ses-actions-de-science-citoyenne-gr-ce-GitHub-Pages-1cae0fff8c678028967fd2f71ebce086)

## Ressources

### Documentation Jekyll
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Minimal Mistakes Documentation](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)

### Science Citoyenne
- [Guide de la Science Participative](https://www.sciences-participatives.com/)
- [Plateforme iNaturalist](https://www.inaturalist.org/)
- [Vigienature](https://www.vigienature.fr/)

## Support

Pour toute question technique sur Jekyll ou GitHub Pages :
- [Jekyll Forum](https://talk.jekyllrb.com/)
- [StackOverflow - Jekyll](https://stackoverflow.com/questions/tagged/jekyll)
- [Documentation GitHub Pages](https://docs.github.com/en/pages)
