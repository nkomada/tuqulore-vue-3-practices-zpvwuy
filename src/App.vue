<script>
import { ref, onMounted } from 'vue';
import ChildComponent from './components/ChildComponent.vue';

export default {
  components: { ChildComponent },
  setup() {
    const shoes = ref([]);
    onMounted(async () => {
      const shoesJson = await fetch('/json/shoes.json');
      shoes.value = await shoesJson.json();
    });
    return { shoes };
  },
};
</script>

<template>
  <ChildComponent v-for="item in shoes.shoes" :shoesData="item" />
</template>

<style>
.card-wrapper {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}
.card {
  border: 1px solid #ccc;
  width: 300px;
}
.thumbnail {
  width: 100%;
}
.item-title {
  font-weight: bold;
  margin-bottom: 0.5rem;
}
.item-description {
  font-size: small;
  margin-bottom: 0.5rem;
}
.item-info {
  padding: 1rem;
}
.item-price {
  font-weight: bold;
  color: orange;
}
</style>
