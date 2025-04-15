<script setup>
defineProps({
  card: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <div class="card">
    <h3>{{ card.name }} {{ card.lastName }}</h3>
  </div>
</template>

<style scoped>
.card {
  padding: 20px;
  background-color: #fff;
  border-radius: 16px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  text-align: center;
  font-size: 18px;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.15);
}
</style>
