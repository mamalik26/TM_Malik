<template>
  <q-page-container>
    <q-page>
      <!-- Bannière ou slider -->
      <div class="banner">
        <h1>Découvrez nos produits frais et locaux !</h1>
        <p>
          Promotions exclusives pour nos clients ! Ingrédients de qualité pour
          des plats savoureux !
        </p>
      </div>

      <!-- Section "Nouveaux produits" -->
      <div class="new-products">
        <h2>Nouveaux arrivages de saison !</h2>
        <p>
          Découvrez nos dernières trouvailles ! N'hésitez pas à essayer quelque
          chose de nouveau !
        </p>
      </div>

      <!-- Menu de navigation -->
      <q-navigation class="menu">
        <h2>Trouvez ce que vous cherchez parmi nos nombreuses catégories !</h2>
        <p>
          Produits locaux et de qualité à portée de clic ! Chaque catégorie
          regorge de délices à découvrir !
        </p>
        <!-- Éléments du menu -->
      </q-navigation>

      <!-- Section "Notre histoire" -->
      <div class="our-story">
        <h2>Apprenez-en plus sur notre ferme et nos fermiers !</h2>
        <p>
          Des pratiques de production respectueuses de l'environnement ! Une
          histoire riche et passionnante !
        </p>
      </div>

      <!-- Section "Comment ça marche?" -->
      <div class="how-it-works">
        <h2>Commander nos produits n'a jamais été aussi simple !</h2>
        <p>
          Livraison rapide et soignée ! Venez découvrir notre système de
          commande en ligne !
        </p>
      </div>
    </q-page>
  </q-page-container>
</template>

<style>
/* Style de la bannière ou du slider */
.banner {
  width: 100%;
  height: 400px;
  background-color: #fff;
  text-align: center;
}

/* Style de la section "Nouveaux produits" */
.new-products {
  width: 80%;
  margin: 0 auto;
  text-align: center;
}

/* Style du menu de navigation */
.menu {
  width: 80%;
  margin: 0 auto;
  text-align: center;
}

/* Style de la section "Notre histoire" */
.our-story {
  width: 80%;
  margin: 0 auto;
  text-align: center;
}

/* Style de la section "Comment ça marche?" */
.how-it-works {
  width: 80%;
  margin: 0 auto;
  text-align: center;
}
</style>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
});
</script>
