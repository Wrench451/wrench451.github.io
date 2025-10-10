---
layout: single
permalink: /
title: Decabock 🌱
---

Chez **Decabock**, nous donnons une seconde vie au bois en créant des objets uniques, où l’esthétique rencontre l’utilité et la personnalisation. Spécialisés dans la fabrication artisanale d’objets en bois, nous mettons notre passion et notre savoir-faire au service de créations durables, conçues pour vous accompagner au quotidien. 
{: .text-justify}

## Notre produit emblématique ? 

**Un dessous de verre ingénieux**, doté d’un décapsuleur intégré et discret, entièrement personnalisable grâce à une gravure sur bois de haute précision. Que ce soit pour offrir un cadeau unique, sublimer une décoration ou simplement ajouter une touche d’élégance à votre intérieur, chaque pièce Decabock est une alliance parfaite entre **fonctionnalité, beauté et singularité**.
{: .text-justify}

<div class="carousel-container">
  <button class="carousel-button prev" onclick="moveSlide(-1, 'carousel-1')">❮</button>
  <div class="carousel" id="DB-carousel">
    <div class="carousel-inner">    
      <div class="carousel-slide">
        <img src="/assets/images/decabock/DB_Aimanté_Twinning_Comitee_Linkded.jpeg" alt="Decabock - Décapsuleur" class="carousel-img">
      </div>
      <div class="carousel-slide">
        <img src="/assets/images/decabock/DB_Twinning_Comitee_Linkded.jpeg" alt="Decabock - Vue de face" class="carousel-img">
      </div>
      <div class="carousel-slide">
        <img src="/assets/images/decabock/DB_Support_Verso_Twinning_Comitee.jpeg" alt="Decabock - Gravure personnalisée" class="carousel-img">
      </div>
    </div>
  </div>
  <button class="carousel-button next" onclick="moveSlide(1, 'carousel-1')">❯</button>
</div>

## Pourquoi choisir Decabock ? 🤔​

- **Artisanat 100% français** 🏡 : Des créations fabriquées localement, avec des matériaux nobles et sélectionnés pour leur durabilité.
- **Personnalisation sur mesure** ​🛠️​ : Gravez vos initiales, un message ou un motif pour un objet qui vous ressemble.
- **Innovation discrète** 🖌️ : Des designs pratiques et élégants, comme notre dessous de verre avec décapsuleur intégré. 
- **Durabilité** 💪 : Des objets conçus pour durer, dans le respect de l’environnement.

## Rejoignez l’aventure Decabock

Vous partagez nos valeurs ? Vous avez envie de soutenir un artisanat **local, éthique et innovant** ? Voici comment nous rejoindre :
{: .text-justify}

- **Découvrez nos créations** : Explorez notre collection et trouvez l’objet qui vous correspond.
- **Personnalisez votre pièce** : Laissez libre cours à votre créativité avec nos options de gravure.
- **Suivez-nous sur les réseaux** : Pour ne rien manquer de nos actualités, conseils et nouveautés.

Chez Decabock, chaque objet raconte une histoire. **Et si la prochaine était la vôtre ?**

<script>
    // Position initiale des carrousels
  let currentSlide = {
    'DB-carousel': 0
  };

  // Fonction pour déplacer les slides
  function moveSlide(step, carouselId) {
    const carousel = document.getElementById(carouselId);
    const slides = carousel.querySelectorAll('.carousel-slide');
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
    carousel.querySelector('.carousel-inner').style.transform = `translateX(-${currentSlide[carouselId] * 100}%)`;
  }
</script>