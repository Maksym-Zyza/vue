<script setup>
import { ref } from "vue";

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
  <div class="hello-wrapper">
    <h2 v-if="flag">Hello!</h2>
    <h2 v-else>Good buy!</h2>

    <h2>{{ name }}</h2>
    <h2>{{ count }}</h2>

    <input type="text" v-model="text" />

    <h3>{{ text }}</h3>

    <button @click="onClick">Click me</button>
    <button @click="onReset">Reset</button>
  </div>
</template>

<style scoped>
h2,
h3 {
  margin: 0;
}
.hello-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 10px;
  padding: 20px 0;
  width: 100%;
  outline: 1px solid teal;
}
</style>
