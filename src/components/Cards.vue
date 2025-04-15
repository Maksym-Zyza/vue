<script setup>
import Card from "./Card.vue";

const cardsList = [
  { name: "Bob", lastName: "Anderson" },
  { name: "Tod", lastName: "Morison" },
  { name: "Li", lastName: "Woo" },
];
</script>

<template>
  <div class="cards-wrapper">
    <h2>Team</h2>
    <ul class="cards">
      <li v-for="card in cardsList" :key="card.name">
        <Card :card="card" />
      </li>
    </ul>
  </div>
</template>

<style scoped>
.cards-wrapper {
  padding: 40px;
  max-width: 960px;
  margin: 0 auto;
  text-align: center;
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 20px;
  list-style: none;
  padding: 0;
  margin-top: 20px;
}
</style>
