<script setup>
import { ref } from "vue";
import Cards from "./components/Cards.vue";

const name = "Max";
const flag = ref(true);
const count = ref(0);
const text = ref("");

const onClick = () => {
  flag.value = !flag.value;
  count.value++;
};
const onReset = () => {
  flag.value = true;
  count.value = 0;
  text.value = "";
};
</script>

<template>
  <div class="container">
    <h2 v-if="flag">Hello!</h2>
    <h2 v-else>Good buy!</h2>
    <h2>{{ name }}</h2>

    <h2>{{ count }}</h2>

    <input type="text" v-model="text" />

    <h3>{{ text }}</h3>

    <button @click="onClick">Click me</button>
    <button @click="onReset">Reset</button>
  </div>

  <Cards />
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 20px;
  width: 100%;
}
</style>
