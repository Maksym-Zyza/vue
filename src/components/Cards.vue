<script setup>
import Card from "./Card.vue";

const cardsList = [
  { name: "Bob", lastName: "Anderson" },
  { name: "Tod", lastName: "Morison" },
  { name: "Li", lastName: "Woo" },
];
</script>

<template>
  <div style="container">Cards SubTitle</div>
  <ul class="cards">
    <li v-for="card in cardsList" :key="card.name">
      <Card :card="card" />
    </li>
  </ul>
</template>

<style scoped>
.container {
  color: blue;
}

.cards {
  background-color: aqua;
}
</style>
