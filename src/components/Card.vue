<script setup>
defineProps({
  card: {
    type: Array,
    required: true,
  },
});
</script>

<template>
  {{ card.name + " " + card.lastName }}
</template>

<style scoped>
.container {
  color: blue;
  font-size: 20px;
}
</style>
