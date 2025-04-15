<script setup>
import SayHello from "./components/SayHello.vue";
import Cards from "./components/Cards.vue";
import LoginForm from "./components/LoginForm.vue";
</script>

<template>
  <div class="container">
    <SayHello />

    <Cards />

    <LoginForm />
  </div>
</template>

<style scoped>
.container {
  width: 90%;
  margin: 5%;
  gap: 20px;
}
</style>
