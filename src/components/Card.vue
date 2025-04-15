<script setup>
import { computed } from "vue";

const props = defineProps({
  card: {
    type: Object,
    required: true,
  },
  discount: {
    type: Number,
    required: true,
  },
});
const finalPrice = computed(() => {
  const { price } = props.card;
  return price - (price * props.discount) / 100;
});
</script>

<template>
  <div class="card">
    <h3>{{ card.name }} {{ card.lastName }}</h3>
    <div>
      Price: <span>{{ card.price }}</span>
    </div>

    <div>
      Discount: <span>{{ card.discount }} %</span>
    </div>
    <div>
      Final price: <span>{{ finalPrice }}</span>
    </div>
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

  > div {
    margin: 10px;
    span {
      width: 40px;
      padding: 2px 8px;
      background: turquoise;
      border-radius: 4px;
    }
  }
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.15);
}
</style>
