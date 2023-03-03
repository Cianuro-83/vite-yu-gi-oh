<template>
  <li>
    <img :src="card.card_images[0].image_url" alt="" class="thumb" />
    <h3 class="name">{{ card.name }}</h3>
    <p>{{ card.archetype }}</p>
  </li>
</template>

<script>
import axios from `axios`;
export default {
  components: {
    axios,
  },
  props: {
    card: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
li {
  h3 {
    color: red;
    text-align: center;
    text-transform: uppercase;
    margin-top: 20px;
  }
  p {
    text-align: center;
    margin-top: 20px;
  }
}
</style>
