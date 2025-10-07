---
permalink: /nous-contacter/
title: "Nous contacter"
layout: single
author_profile: true
---

Chez **Decabock**, nous croyons que chaque objet en bois raconte une histoire — la vôtre. Que vous souhaitiez **personnaliser une pièce**, découvrir nos dernières créations ou simplement échanger avec notre équipe, nous sommes à votre écoute.

En nous contactant, vous bénéficiez de :
- **Des promotions exclusives** réservées à nos abonnés.
- **Un accès en avant-première** à nos nouveaux modèles et designs.
- **Un accompagnement personnalisé** pour créer un objet unique, à votre image.

N’hésitez pas à nous écrire via le formulaire ci-dessous ou à nous suivre sur les réseaux sociaux pour ne rien manquer de l’aventure Decabock.

## Pourquoi nous contacter ?

| Avantages | Détails |
|:---------:|:--------|
| **Promotions exclusives** | Bénéficiez de réductions spéciales sur nos collections, réservées à nos contacts privilégiés. |
| **Avant-premières** | Soyez les premiers informés de nos nouvelles créations et lancez-vous avant tout le monde. |
| **Personnalisation sur mesure** | Nous vous accompagnons pour créer un objet unique, gravé ou conçu selon vos envies. |
| **Conseils d’experts** | Besoin d’aide pour choisir ? Notre équipe vous guide pour trouver la pièce parfaite. |

## Formulaire de contact

Remplissez le formulaire ci-dessous pour nous envoyer un message. Nous vous répondrons dans les **24 à 48 heures**.

<form id="contact-form" class="contact-form">
  <!-- Légende pour les champs obligatoires -->
  <p class="required-legend"><span class="required-star">*</span> Champs obligatoires</p>

  <!-- Champ : Nom -->
  <div class="form-group">
    <label for="nom">Nom <span class="required-star">*</span></label>
    <input type="text" id="nom" name="nom" placeholder="Votre nom" required class="form-control">
  </div>

  <!-- Champ : Prénom -->
  <div class="form-group">
    <label for="prenom">Prénom <span class="required-star">*</span></label>
    <input type="text" id="prenom" name="prenom" placeholder="Votre prénom" required class="form-control">
  </div>

  <!-- Champ : Type de demande -->
  <div class="form-group">
    <label for="type-demande">Type de demande <span class="required-star">*</span></label>
    <select id="type-demande" name="type-demande" required class="form-control">
      <option value="" disabled selected>Sélectionnez un type de demande</option>
      <option value="Personnalisation">Personnalisation d’un produit</option>
      <option value="Question">Question sur un produit</option>
      <option value="Partenariat">Demande de partenariat</option>
      <option value="Autre">Autre</option>
    </select>
  </div>

  <!-- Champ : Objet de la demande -->
  <div class="form-group">
    <label for="objet">Objet de la demande <span class="required-star">*</span></label>
    <input type="text" id="objet" name="objet" placeholder="Précisez l’objet de votre demande" required class="form-control">
  </div>

  <!-- Champ : Message -->
  <div class="form-group">
    <label for="message">Message <span class="required-star">*</span></label>
    <textarea id="message" name="message" placeholder="Votre message..." required rows="5" class="form-control"></textarea>
  </div>

  <!-- Bouton d'envoi -->
  <div class="form-group">
    <button type="button" onclick="sendEmail()" class="btn-submit">
      Envoyer le message
    </button>
  </div>
</form>

## Autres moyens de nous contacter

<table>
  <thead>
    <tr>
      <th>Canal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><i class="fas fa-fw fa-envelope"></i><a href="mailto:pcarteron.decabock@gmail.com"> pcarteron.decabock@gmail.com</a></td>
    </tr>
    <tr>
      <td><i class="fas fa-fw fa-phone"></i><a href="tel:+33782702672"> +33 7 82 70 26 72</a> (du lundi au vendredi, 9h-18h)</td>
    </tr>
    <tr>
      <td><i class="fab fa-fw fa-instagram"></i><a href="https://www.instagram.com/decabock_fr/" target="_blank"> Instagram</a></td>
    </tr>
    <tr>
      <td><i class="fab fa-fw fa-facebook"></i><a href="https://www.facebook.com/profile.php?id=61569670629084" target="_blank"> Facebook</a></td>
    </tr>
    <tr>
      <td><i class="fab fa-fw fa-linkedin"></i><a href="https://www.linkedin.com/company/decabock" target="_blank"> LinkedIn</a></td>
    </tr>
  </tbody>
</table>


{% raw %}
<script>
  function sendEmail() {
    // Récupérer les valeurs des champs
    const nom = document.getElementById("nom").value;
    const prenom = document.getElementById("prenom").value;
    const typeDemande = document.getElementById("type-demande").value;
    const typeDemandeText = typeDemande.options[typeDemande.selectedIndex].text;
    const objet = document.getElementById("objet").value;
    const message = document.getElementById("message").value;

    // Construire le lien mailto
    const subject = encodeURIComponent(`[Decabock] ${typeDemande} : ${objet}`);
    const body = encodeURIComponent(
      `Bonjour,\n\n` + 
      `Je m'appelle ${prenom} ${nom} et je vous contacte concernant : ${typeDemandeText}.` + 
      `\n\nObjet : ${objet}` + 
      `\n\nMessage : ${message}` + 
      `\n\nCordialement,` + 
      `\n\n ${nom} ${prenom}`
    );

    // Ouvrir le client mail
    window.location.href = `mailto:pcarteron.decabock@gmail.com?subject=${subject}&body=${body}`;
  }
</script>
{% endraw %}
