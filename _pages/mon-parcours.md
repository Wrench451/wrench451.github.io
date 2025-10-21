---
layout: single
title: "Mon parcours professionnel 🚶‍➡️"
permalink: /mon-parcours/
author_profile: true
toc: false
classes: wide
---

<div id="timeline" class="timeline">

</div>

<script>
  // === timeline.js ===
// Charge le fichier JSON et génère dynamiquement la timeline

async function loadTimeline() {
  try {
    const response = await fetch('/assets/data/parcours.json');
    if (!response.ok) throw new Error('Erreur lors du chargement du parcours professionnel');

    const parcours = await response.json();
    const timelineContainer = document.getElementById('timeline');

    // Vider le conteneur avant d'insérer les items
    timelineContainer.innerHTML = '';

    // Génération dynamique des éléments de timeline
    parcours.forEach(item => {
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
  } catch (error) {
    console.error(error);
    document.getElementById('timeline').innerHTML =
      '<p class="error">Impossible de charger le parcours professionnel.</p>';
  }
}

// Lancement au chargement du DOM
document.addEventListener('DOMContentLoaded', loadTimeline);

</script>