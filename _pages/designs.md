---
title: "Nos Designs 🎨"
layout: single
permalink: /designs/
---

Découvrez tous nos **designs personnalisables** pour sublimer vos produits Decabock. Chaque design est disponible sur un ou plusieurs produits.

## **Nos Créations personnelles**

<div class="designs-grid">

</div>

<script>
  // Position initiale des carrousels
  let currentSlide = {};

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

  // Fonction pour charger le fichier JSON
  async function loadDesigns() {
    try {
      const response = await fetch('/assets/data/designs.json');
      if (!response.ok) {
        throw new Error('Erreur lors du chargement des designs');
      }
      const designs = await response.json();
      console.log(designs);
      generateDesignCards(designs);
    } catch (error) {
      console.error('Erreur:', error);
    }
  }

  // Fonction pour générer les cartes de designs
  function generateDesignCards(designs) {
    const designsGrid = document.querySelector('.designs-grid');

    designs.forEach((design) => {
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

  // Charger les designs au chargement de la page
  document.addEventListener("DOMContentLoaded", loadDesigns);
</script>
