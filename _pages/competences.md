---
permalink: /competences/
title: "Mes compétences ⚙️"
layout: single
author_profile: true
toc: false
classes: wide
---

### Compétences techniques

<div id="skills-tech" class="skills-container">

</div>

### Soft Skills

<div id="skills-soft" class="skills-container">

</div>

<script>
  // Génère dynamiquement les compétences techniques et soft skills

  async function loadCompetences() {
    try {
      const response = await fetch('/assets/data/competences.json');
      if (!response.ok) throw new Error('Erreur lors du chargement des compétences');

      const data = await response.json();

      // Sélecteurs des conteneurs
      const techContainer = document.getElementById('skills-tech');
      const softContainer = document.getElementById('skills-soft');

      // Nettoyage initial
      techContainer.innerHTML = '';
      softContainer.innerHTML = '';

      // Fonction pour créer une "barre de progression"
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

      // Génération des compétences techniques
      data.techniques.forEach(skill => {
        techContainer.appendChild(createSkill(skill));
      });

      // Génération des soft skills
      data.softskills.forEach(skill => {
        softContainer.appendChild(createSkill(skill));
      });

    } catch (error) {
      console.error(error);
      const errorMsg = '<p class="error">Impossible de charger les compétences.</p>';
      document.getElementById('skills-tech').innerHTML = errorMsg;
      document.getElementById('skills-soft').innerHTML = errorMsg;
    }
  }

  // Charger au démarrage
  document.addEventListener('DOMContentLoaded', loadCompetences);
</script>