<template>
  <div class="container">
    <input
      @keydown.enter="$emit(`inRicerca`)"
      type="text"
      class="input-filtro"
      v-model="store.cerca"
      placeholder="Filtra card per nome"
    />
  </div>
</template>

<script>
import store from "../store";
export default {
  data() {
    return {
      store,
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
.input-filtro {
  line-height: 2rem;
  border-radius: 5px;
  margin: 15px 0;
  padding: 0 10px;
  width: 250px;
}
</style>
