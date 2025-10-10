---
title: "Nos Designs 🎨"
layout: single
permalink: /designs/
---

Découvrez tous nos **designs personnalisables** pour sublimer vos produits Decabock. Chaque design est disponible sur un ou plusieurs produits.

## Nos Créations personnelles <span id="design-count">(0) designs dispobiles</span>
### Filtrer par produit
<div class="filter-container">
  <button class="filter-button active" data-filter="all">Tous</button>
  <button class="filter-button" data-filter="Decabock">Decabock</button>
  <button class="filter-button" data-filter="Bouchons de vin">Bouchons de vin</button>
  <!-- <button class="filter-button" data-filter="Planche à découper">Planche à découper</button>
  <button class="filter-button" data-filter="Porte-clés">Porte-clés</button> -->
</div>

<div class="designs-grid">

</div>

<script>
  // Position initiale des carrousels
  let currentSlide = {};
  let allDesigns = []; // Stocke tous les designs
  let activeFilters = new Set(); // Stocke les filtres actifs

  // Fonction pour déplacer les slides
  function moveSlide(step, carouselId) {
    if (!currentSlide[carouselId]) {
      currentSlide[carouselId] = 0;
    }
    
    const carousel = document.getElementById(carouselId);
    const slides = carousel.querySelectorAll('.design-carousel-slide');
    const totalSlides = slides.length;

    // Mise à jour de la position actuelle
    currentSlide[carouselId] += step;

    // Gestion des limites
    if (currentSlide[carouselId] < 0) {
      currentSlide[carouselId] = totalSlides - 1;
    } else if (currentSlide[carouselId] >= totalSlides) {
      currentSlide[carouselId] = 0;
    }

    // Déplacement du carrousel
    carousel.querySelector('.design-carousel-inner').style.transform = `translateX(-${currentSlide[carouselId] * 100}%)`;
  }

  // Fonction pour filtrer les designs
  function filterDesigns() {
    const designsGrid = document.querySelector('.designs-grid');
    designsGrid.innerHTML = ''; // Vide la grille

    let filteredDesigns = allDesigns;

    // Si aucun filtre n'est actif ou si "Tous" est sélectionné
    if (activeFilters.size === 0 || activeFilters.has('all')) {
      filteredDesigns = allDesigns;
    } else {
      // Filtrer les designs qui correspondent à tous les filtres actifs
      filteredDesigns = allDesigns.filter(design =>
        Array.from(activeFilters).every(filter =>
          design.products.includes(filter)
        )
      );
    }

    // Mettre à jour le compteur de designs
    document.getElementById('design-count').textContent = `(${filteredDesigns.length})`;

    if (filteredDesigns.length === 0) {
      designsGrid.innerHTML = '<p class="no-results">Aucun design disponible pour ces produits.</p>';
      return;
    }

    filteredDesigns.forEach((design) => {
      const designCard = document.createElement('div');
      designCard.className = 'design-card';
      designCard.innerHTML = `
        <div class="design-header">
          <h3 class="design-name">${design.name}</h3>
          <p class="design-id">🆔 ID: ${design.id}</p>
        </div>
        <div class="design-carousel-container">
          <div class="design-carousel" id="carousel-${design.id}">
            <div class="design-carousel-inner">
              ${design.images.map((image, imgIndex) => `
                <div class="design-carousel-slide">
                  <img src="${image}" alt="${design.name} - Vue ${imgIndex + 1}" class="design-carousel-img">
                </div>
              `).join('')}
            </div>
          </div>
          <button class="design-carousel-button prev" onclick="moveSlide(-1, 'carousel-${design.id}')">❮</button>
          <button class="design-carousel-button next" onclick="moveSlide(1, 'carousel-${design.id}')">❯</button>
        </div>
        <p class="design-products">📌 Disponible sur : ${design.products.join(', ')}</p>
      `;
      designsGrid.appendChild(designCard);
    });
  }

  // Fonction pour charger le fichier JSON
  async function loadDesigns() {
    try {
      const response = await fetch('/assets/data/designs.json');
      if (!response.ok) {
        throw new Error('Erreur lors du chargement des designs');
      }
      allDesigns = await response.json();
      filterDesigns(); // Affiche tous les designs au chargement
    } catch (error) {
      console.error('Erreur:', error);
    }
  }

  // Charger les designs au chargement de la page
  document.addEventListener("DOMContentLoaded", () => {
    loadDesigns();

    // Ajouter les écouteurs d'événements aux boutons de filtrage
    document.querySelectorAll('.filter-button').forEach(button => {
      button.addEventListener('click', () => {
        // Si le bouton "Tous" est cliqué
        if (button.dataset.filter === 'all') {
          // Réinitialiser les filtres
          activeFilters.clear();
          document.querySelectorAll('.filter-button').forEach(btn => btn.classList.remove('active'));
          button.classList.add('active');
          filterDesigns();
          return;
        }

        // Basculer l'état actif du bouton
        button.classList.toggle('active');

        // Si le bouton est actif, ajouter le filtre
        if (button.classList.contains('active')) {
          activeFilters.add(button.dataset.filter);
        } else {
          // Sinon, retirer le filtre
          activeFilters.delete(button.dataset.filter);
        }

        // Si aucun filtre n'est actif, réactiver "Tous"
        if (activeFilters.size === 0) {
          document.querySelector('.filter-button[data-filter="all"]').classList.add('active');
        } else {
          // Désactiver "Tous" si d'autres filtres sont actifs
          document.querySelector('.filter-button[data-filter="all"]').classList.remove('active');
        }

        // Appliquer les filtres
        filterDesigns();
      });
    });
  });
</script>