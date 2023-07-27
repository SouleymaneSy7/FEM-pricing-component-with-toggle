<template>
  <h1 class="main__title">Our Pricing</h1>

  <!-- CheckBox  -->
  <section class="checkbox-container">
    <p class="sm__font">Annually</p>

    <div
      class="checkbox"
      @click="priceToggle()"
      :class="monthly === true ? 'active' : ''"
    >
      <div class="checkbox-toggle"></div>
    </div>

    <p class="sm__font">Monthly</p>
  </section>

  <!-- Card -->
  <section class="card-container">
    <article class="card" v-for="card in cards" :key="card.cardId">
      <p class="base__font">{{ card.cardType }}</p>

      <h2 class="price" v-if="monthly">
        <span class="dollar-sign">&dollar;</span> {{ card.cardPriceMonthly }}
      </h2>
      <h2 class="price" v-else>
        <span class="dollar-sign">&dollar;</span>{{ card.cardPriceAnnualy }}
      </h2>

      <div class="card__table">
        <p class="base__font">{{ card.cardText1 }}</p>
        <p class="base__font">{{ card.cardText2 }}</p>
        <p class="base__font">{{ card.cardText3 }}</p>
      </div>

      <button type="button" class="btn">{{ card.cardBtnText }}</button>
    </article>
  </section>

  <footer class="attribution">
    <p>
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
        >Frontend Mentor</a
      >
    </p>

    <p>
      Code <span>&hearts;</span> by
      <a href="https://github.com/SouleymaneSy7" target="_blank"
        >Souleymane Sy</a
      >
    </p>
  </footer>
</template>

<script setup>
// Imports
import { ref } from "vue";

// Variables
const monthly = ref(false);
const cards = ref([
  {
    cardId: 1,
    cardType: "Basic",
    cardPriceAnnualy: 199.99,
    cardPriceMonthly: 19.99,
    cardText1: "500 GB Storage",
    cardText2: "2 Users Allowed",
    cardText3: "Send up to 3 GB",
    cardBtnText: "Learn More",
  },
  {
    cardId: 2,
    cardType: "Professional",
    cardPriceAnnualy: 249.99,
    cardPriceMonthly: 24.99,
    cardText1: "1 TB Storage",
    cardText2: "5 Users Allowed",
    cardText3: "Send up to 10 GB",
    cardBtnText: "Learn More",
  },
  {
    cardId: 3,
    cardType: "Master",
    cardPriceAnnualy: 399.99,
    cardPriceMonthly: 39.99,
    cardText1: "2 TB Storage",
    cardText2: "10 Users Allowed",
    cardText3: "Send up to 20 GB",
    cardBtnText: "Learn More",
  },
]);

// Functions
const priceToggle = () => {
  monthly.value = !monthly.value;
};
</script>
