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

<div id="timeline" class="timeline">

</div>

Pour découvrir **mon parcours professionnel complet**, [clique ici](mon-parcours).

## Mes compétences et soft skills

### Compétences techniques

<div id="skills-tech" class="skills-container">

</div>

### Soft Skills

<div id="skills-soft" class="skills-container">

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
  // === Timeline et Compétences pour la page d'accueil ===

  async function loadTimeline() {
    try {
      const response = await fetch('/assets/data/parcours.json');
      if (!response.ok) throw new Error('Erreur lors du chargement du parcours professionnel');

      const parcours = await response.json();
      const timelineContainer = document.getElementById('timeline');
      timelineContainer.innerHTML = '';

      const parcoursToShow = parcours.slice(0, 3); // 3 expériences max

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

  async function loadCompetences() {
    try {
      const response = await fetch('/assets/data/competences.json');
      if (!response.ok) throw new Error('Erreur lors du chargement des compétences');

      const data = await response.json();
      const techContainer = document.getElementById('skills-tech');
      const softContainer = document.getElementById('skills-soft');

      techContainer.innerHTML = '';
      softContainer.innerHTML = '';

      const createSkill = (skill) => {
        const progress = document.createElement('div');
        progress.className = 'progress';
        progress.innerHTML = `
          <div class="barOverflow">
            <div class="bar" style="--r: ${skill.niveau}"></div>
          </div>
          <span>${skill.niveau}</span>%
          <p>${skill.nom}</p>
          ${skill.hint ? `<div class="hint">${skill.hint}</div>` : ''}
        `;
        return progress;
      };

      // Afficher seulement les 4 premières compétences techniques
      const techToShow = data.techniques.slice(0, 4);
      techToShow.forEach(skill => techContainer.appendChild(createSkill(skill)));

      // Message sur le nombre de compétences restantes
      const remainingTech = data.techniques.length - techToShow.length;
      if (remainingTech > 0) {
        const moreTech = document.createElement('p');
        moreTech.className = 'skills-more';
        moreTech.innerHTML = `...et ${remainingTech} compétence(s) technique(s) supplémentaire(s)`;
        techContainer.appendChild(moreTech);
      }

      // Afficher seulement les 4 premières soft skills
      const softToShow = data.softskills.slice(0, 4);
      softToShow.forEach(skill => softContainer.appendChild(createSkill(skill)));

      // Message sur le nombre de soft skills restantes
      const remainingSoft = data.softskills.length - softToShow.length;
      if (remainingSoft > 0) {
        const moreSoft = document.createElement('p');
        moreSoft.className = 'skills-more';
        moreSoft.innerHTML = `...et ${remainingSoft} soft skill(s) supplémentaire(s)`;
        softContainer.appendChild(moreSoft);
      }

    } catch (error) {
      console.error(error);
      const errorMsg = '<p class="error">Impossible de charger les compétences.</p>';
      document.getElementById('skills-tech').innerHTML = errorMsg;
      document.getElementById('skills-soft').innerHTML = errorMsg;
    }
  }

  // Lancer au chargement du DOM
  document.addEventListener('DOMContentLoaded', () => {
    loadTimeline();
    loadCompetences();
  });
</script>