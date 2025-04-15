<script setup>
import Card from "./Card.vue";
import { ref } from "vue";

const cardsList = [
  { name: "Bob", lastName: "Anderson", price: 200 },
  { name: "Tod", lastName: "Morison", price: 170 },
  { name: "Li", lastName: "Woo", price: 120 },
];

const discount = ref(0);
</script>

<template>
  <div class="cards-wrapper">
    <h2>Cards:</h2>

    <div>Discount, %:</div>
    <input type="text" v-model="discount" />

    <ul class="cards">
      <li v-for="card in cardsList" :key="card.name">
        <Card :card="card" :discount="discount" />
      </li>
    </ul>
  </div>
</template>

<style scoped>
.cards-wrapper {
  margin: 5%;
  width: 100%;
  margin: 10px auto;
  padding: 10px 0;
  text-align: center;
  outline: 1px solid teal;

  div {
    margin: 4px;
  }
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
