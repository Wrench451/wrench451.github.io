---
title: "Nos Designs"
layout: single
permalink: /designs/
---

# 🎨 Catalogue des Designs Disponibles

Découvrez tous nos **designs personnalisables** pour sublimer vos produits Decabock. Chaque design est disponible sur un ou plusieurs produits.

---

## **Nos Créations**

<div class="designs-grid">
  <!-- Design 1 -->
  <div class="design-card">
    <h3 class="design-name">Bientôt super tata & tonton</h3>
    <p class="design-id">📛 ID: DB-001</p>
    <div class="design-carousel-container">
      <div class="design-carousel" id="carousel-DB-001">
        <div class="design-carousel-inner">
          <div class="design-carousel-slide">
            <img src="/assets/images/designs/bientot_tata_tonton/Bientôt_super_tata_&_tonton.png" alt="Bientôt super tata & tonton - Vue 1" class="design-carousel-img">
          </div>
          <div class="design-carousel-slide">
            <img src="/assets/images/designs/defApero.jpg" alt="Bientôt super tata & tonton - Vue 2" class="design-carousel-img">
          </div>
        </div>
      </div>
      <button class="design-carousel-button prev" onclick="moveSlide(-1, 'carousel-DB-001')">❮</button>
      <button class="design-carousel-button next" onclick="moveSlide(1, 'carousel-DB-001')">❯</button>
    </div>
    <p class="design-products">📌 Disponible sur : Bouchons de vin, Decabock</p>
  </div>

  <!-- Design 2 -->
  <div class="design-card">
    <h3 class="design-name">C'est pas l'homme qui prends l'apéro</h3>
    <p class="design-id">📛 ID: DB-002</p>
    <div class="design-carousel-container">
      <div class="design-carousel" id="carousel-DB-002">
        <div class="design-carousel-inner">
          <div class="design-carousel-slide">
            <img src="/assets/images/designs/homme_prends_apero/C&apos;est l&apos;apéro qui prends l&apos;homme.png" alt="C'est pas l'homme qui prends l'apéro - Vue 1" class="design-carousel-img">
          </div>
          <div class="design-carousel-slide">
            <img src="/assets/images/designs/defApero.jpg" alt="C'est pas l'homme qui prends l'apéro - Vue 2" class="design-carousel-img">
          </div>
        </div>
      </div>
      <button class="design-carousel-button prev" onclick="moveSlide(-1, 'carousel-DB-002')">❮</button>
      <button class="design-carousel-button next" onclick="moveSlide(1, 'carousel-DB-002')">❯</button>
    </div>
    <p class="design-products">📌 Disponible sur : Decabock</p>
  </div>

  <!-- Design 3 -->
  <div class="design-card">
    <h3 class="design-name">C'est pas versailles ici</h3>
    <p class="design-id">📛 ID: DB-003</p>
    <div class="design-carousel-container">
      <div class="design-carousel" id="carousel-DB-003">
        <div class="design-carousel-inner">
          <div class="design-carousel-slide">
            <img src="/assets/images/designs/pas_versailles/C&apos;est pas versailles ici.png" alt="C'est pas versailles ici - Vue 1" class="design-carousel-img">
          </div>
          <div class="design-carousel-slide">
            <img src="/assets/images/designs/defApero.jpg" alt="C'est pas versailles ici - Vue 2" class="design-carousel-img">
          </div>
        </div>
      </div>
      <button class="design-carousel-button prev" onclick="moveSlide(-1, 'carousel-DB-003')">❮</button>
      <button class="design-carousel-button next" onclick="moveSlide(1, 'carousel-DB-003')">❯</button>
    </div>
    <p class="design-products">📌 Disponible sur : Bouchons de vin, Decabock</p>
  </div>

  <!-- Design 4 -->
  <div class="design-card">
    <h3 class="design-name">Family</h3>
    <p class="design-id">📛 ID: DB-004</p>
    <div class="design-carousel-container">
      <div class="design-carousel" id="carousel-DB-004">
        <div class="design-carousel-inner">
          <div class="design-carousel-slide">
            <img src="/assets/images/designs/family/Family_full.png" alt="Family - Vue 1" class="design-carousel-img">
          </div>
          <div class="design-carousel-slide">
            <img src="/assets/images/designs/defApero.jpg" alt="Family - Vue 2" class="design-carousel-img">
          </div>
        </div>
      </div>
      <button class="design-carousel-button prev" onclick="moveSlide(-1, 'carousel-DB-004')">❮</button>
      <button class="design-carousel-button next" onclick="moveSlide(1, 'carousel-DB-004')">❯</button>
    </div>
    <p class="design-products">📌 Disponible sur : Bouchons de vin, Decabock</p>
  </div>
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
</script>
