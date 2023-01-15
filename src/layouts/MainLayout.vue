<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-primary text-white" height-hint="120">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>
          <q-avatar>
            <img src="/TM_Malik/public/icons/logo_TM_2.png" alt="Logo"/>
          </q-avatar>
          Latifundia
        </q-toolbar-title>
        <div class="q-px-lg q-pt-xxxl"></div>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <!-- contenu drawer-->

      <!-- Champ de recherche -->
      <div class="search-field">
        <q-input v-model="searchTerm" placeholder="Rechercher un produit" />
      </div>

      <!-- Section "Mon compte" -->
      <q-item clickable>
        <q-item-section> Mon compte </q-item-section>
      </q-item>

      <!-- Section "Panier" -->
      <q-item clickable>
        <q-item-section> Panier </q-item-section>
      </q-item>

      <!-- Section "Fruits et légumes" -->
      <q-item clickable>
        <q-item-section> Fruits et légumes </q-item-section>
      </q-item>

      <!-- Section "Boulangeries" -->
      <q-item clickable>
        <q-item-section> Boulangeries </q-item-section>
      </q-item>

      <!-- Section "Viandes et poissons" -->
      <q-item clickable>
        <q-item-section> Viandes et poissons </q-item-section>
      </q-item>

      <!-- Section "Produits laitiers" -->
      <q-item clickable>
        <q-item-section> Produits laitiers </q-item-section>
      </q-item>

      <!-- Section "boissons" -->
      <q-item clickable>
        <q-item-section> Boissons </q-item-section>
      </q-item>

      <!-- Section "Autres" -->
      <q-item clickable>
        <q-item-section> Autres </q-item-section>
      </q-item>

    </q-drawer>

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
            Découvrez nos dernières trouvailles ! N'hésitez pas à essayer
            quelque chose de nouveau !
          </p>

          <div class="q-pa-md">
    <div class="q-gutter-md">
      <q-carousel
        v-model="slide"
        transition-prev="scale"
        transition-next="scale"
        swipeable
        animated
        control-color="black"
        navigation
        padding
        arrows
        height="300px"
        class="bg-primary text-white shadow-1 rounded-borders"
      >
        <q-carousel-slide name="style" class="column no-wrap flex-center">
          <q-icon name="style" size="56px" />
          <div class="q-mt-md text-center">
            {{ lorem }}
          </div>
        </q-carousel-slide>
        <q-carousel-slide name="tv" class="column no-wrap flex-center">
          <q-icon name="live_tv" size="56px" />
          <div class="q-mt-md text-center">
            {{ lorem }}
          </div>
        </q-carousel-slide>
        <q-carousel-slide name="layers" class="column no-wrap flex-center">
          <q-icon name="layers" size="56px" />
          <div class="q-mt-md text-center">
            {{ lorem }}
          </div>
        </q-carousel-slide>
        <q-carousel-slide name="map" class="column no-wrap flex-center">
          <q-icon name="terrain" size="56px" />
          <div class="q-mt-md text-center">
            {{ lorem }}
          </div>
        </q-carousel-slide>
      </q-carousel>
    </div>
  </div>

        </div>

        <!-- Menu de navigation -->
        <q-navigation class="menu">
          <h2>
            Trouvez ce que vous cherchez parmi nos nombreuses catégories !
          </h2>
          <p>
            Produits locaux et de qualité à portée de clic ! Chaque catégorie
            regorge de délices à découvrir !
          </p>
          <!-- Éléments du menu -->
        </q-navigation>

        <!-- Section "Comment ça marche?" -->
        <div class="how-it-works">
          <h2>Comment commander sur notre site ?</h2>
          <p>
            1. Parcourez notre catalogue de produits et ajoutez ceux qui vous
            intéressent à votre panier en cliquant sur le bouton "Ajouter au
            panier".<br>2. Une fois que vous avez ajouté tous les produits que vous
            souhaitez acheter, cliquez sur le bouton "Passer la commande"<br>3. Suivez les étapes pour finaliser votre commande et choisir
            votre mode de paiement.<br>4. Nous nous occupons du reste ! Nous préparons votre commande
            avec soin et nous veillons à ce qu'elle vous soit livrée dans
            les meilleurs délais.
          </p>
        </div>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref, watch } from 'vue'
import db from '/db.json'

export default {
  data() {
    return {
      searchTerm: "",
      leftDrawerOpen: false
    };
    return {
        products: db.products,
      };
  },
  methods: {
    toggleLeftDrawer() {
      this.leftDrawerOpen = !this.leftDrawerOpen;
    }
  },
  setup () {
    const navPos = ref('bottom')
    const vertical = ref(false)
    watch(vertical, val => {
      navPos.value = val === true
        ? 'right'
        : 'bottom'
    })
    return {
      slide: ref('style'),
      lorem: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo.'
    }
  }
}
</script>

<style>

.search-field {
  margin: 16px;
  width: 200px;
}

.banner {
  height: 300px;
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.new-products {
  height: 600px;
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.menu {
  height: 300px;
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.our-story {
  height: 300px;
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.how-it-works {
  height: 300px;
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}


.invisible {
  display: none;
}
</style>
