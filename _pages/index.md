---
layout: single
permalink: /
title: Qui suis-je ? 💻​
classes: wide
---

Je m’appelle **Pierre Carteron**, j’ai 21 ans (né le 22 décembre 2003) et je suis actuellement en alternance au **CESI École d’Ingénieurs** à La Rochelle, tout en travaillant chez **Euro-Information** à Orléans en tant que analyste développeur.
{: .text-justify}
Passionné par l’informatique depuis le collège, je suis curieux depuis tout petit. J’aime **apprendre**, **découvrir** et **explorer** tout système, simple comme complexe.
{: .text-justify}

## Mon parcours professionnel récent

<div class="timeline">

</div>

Pour découvrir **mon parcours professionnel complet**, [clique ici](mon-parcours).

## Mes compétences et soft skills

### Compétences techniques

<div class="skills-container">
  <div class="progress">
    <div class="barOverflow">
      <div class="bar" style="--r : 80"></div>
    </div>
    <span>80</span>%
    <p>Développement Web</p>
  </div>
  <div class="progress">
    <div class="barOverflow">
      <div class="bar" style="--r : 90"></div>
    </div>
    <span>90</span>%
    <p>Développement logiciel</p>
  </div>
  <div class="progress">
    <div class="barOverflow">
      <div class="bar" style="--r : 75"></div>
    </div>
    <span>75</span>%
    <p>Base de données</p>
  </div>
  <div class="progress">
    <div class="barOverflow">
      <div class="bar" style="--r: 95"></div>
    </div>
    <span>95</span>%
    <p>Anglais</p>
    <div class="hint">
      Niveau avancé au TOEIC : 810/990.
    </div>
  </div>
</div>

### Soft Skills
<div class="skills-container">
  <div class="progress">
    <div class="barOverflow">
      <div class="bar" style="--r : 90"></div>
    </div>
    <span>90</span>%
    <p>Travail d'équipe</p>
  </div>
  <div class="progress">
    <div class="barOverflow">
      <div class="bar" style="--r : 95"></div>
    </div>
    <span>95</span>%
    <p>Résolution de problèmes</p>
  </div>
  <div class="progress">
    <div class="barOverflow">
      <div class="bar" style="--r : 85"></div>
    </div>
    <span>85</span>%
    <p>Adaptabilité</p>
  </div>
  <div class="progress">
    <div class="barOverflow">
      <div class="bar" style="--r : 80"></div>
    </div>
    <span>80</span>%
    <p>Créativité</p>
  </div>
</div>

Pour voir la **liste complète de mes compétences**, [clique ici](competences).

## Mes 3 derniers projets

### 1. [Création d’un site statique de présentation pour Decabock](projets/decabock-site)
**Technologies** : Markdown, Jekyll, Minimal Mistakes<br>
**Description** : Conception d’un site vitrine statique pour mon entreprise *Decabock*, visant à améliorer sa visibilité en ligne grâce à un nom de domaine personnalisé. Le site présente les produits, les designs et les services de manière claire et élégante.<br>
**Résultats** : Amélioration de la présence en ligne et meilleure accessibilité des informations pour les clients.<br>

### 2. [Développement d’un site web dynamique “Mangeur Kiffeur”](projets/mangeur-kiffeur)
**Technologies** : React, Next.js, MongoDB<br>
**Description** : Réalisation d’un site web inspiré d’Uber Eats dans le cadre d’un projet scolaire en équipe. Ce projet inclut la gestion de bases de données pour les restaurants, les utilisateurs et les administrateurs, ainsi que la conception des interfaces et de l’architecture applicative.<br>
**Résultats** : Application fonctionnelle permettant la gestion complète des commandes et des utilisateurs, validée lors du projet académique.<br>


### 3. [Création d’un Photobooth éco-responsable – Nuit de l’Info 2023](projets/photobooth-ndi)
**Technologies** : Python, Raspberry Pi, Électronique embarquée<br>
**Description** : Conception et fabrication d’un photobooth DIY éco-responsable dans le cadre de la *Nuit de l’Info 2023*. Le projet combinait la construction physique de la borne (bois et électronique) et le développement d’une application interne sur Raspberry Pi.<br>
**Résultats** : Projet lauréat du défi éco-responsable, salué pour son innovation et son intégration matériel-logiciel.<br>

Pour découvrir **tous mes projets**, [clique ici](projets).

<script>
  // Charge le fichier JSON et génère dynamiquement la timeline

  async function loadTimeline() {
    try {
      const response = await fetch('/assets/data/parcours.json');
      if (!response.ok) throw new Error('Erreur lors du chargement du parcours professionnel');

      const parcours = await response.json();
      const timelineContainer = document.getElementById('timeline');

      // Vider le conteneur avant d'insérer les items
      timelineContainer.innerHTML = '';

      // Afficher seulement les 3 premiers éléments (les plus récents)
      const parcoursToShow = parcours.slice(0, 3);

      parcoursToShow.forEach(item => {
        const timelineItem = document.createElement('div');
        timelineItem.className = 'timeline-item';
        timelineItem.innerHTML = `
          <div class="timeline-date">${item.date}</div>
          <div class="timeline-content">
            <h3>${item.poste}</h3>
            <p class="timeline-subtitle">${item.entreprise}</p>
            <p class="timeline-description">${item.description}</p>
          </div>
        `;
        timelineContainer.appendChild(timelineItem);
      });

      // Si tu veux indiquer qu’il existe d’autres expériences :
      if (parcours.length > 3) {
        const moreNotice = document.createElement('p');
        moreNotice.className = 'timeline-more';
        moreNotice.innerHTML = `...et ${parcours.length - 3} autres expériences à découvrir`;
        timelineContainer.appendChild(moreNotice);
      }

    } catch (error) {
      console.error(error);
      document.getElementById('timeline').innerHTML =
        '<p class="error">Impossible de charger le parcours professionnel.</p>';
    }
  }

  // Lancement au chargement du DOM
  document.addEventListener('DOMContentLoaded', loadTimeline);
</script>
