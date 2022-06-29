<template>
  <div class="card">
    <!-- <img class="thumbnail" :src="'/img/items/' + item.photoFileName" alt="" /> -->
    <img class="thumbnail" :src="'https://raw.githubusercontent.com/tuqulore/vue-3-practices/main/handson-gallery-shoes/public/img/items/' + item.photoFileName" alt="" />
    {{ item.name }}
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  props: {
    shoesData: Object,
  },
  setup(props) {
    const item = ref(props.shoesData);
    return {
      item,
    };
  },
};
</script>
