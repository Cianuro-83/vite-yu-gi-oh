<template>
  <div class="container">
    <div class="input">
      <input
        @keydown.enter="$emit(`inRicerca`)"
        type="text"
        class="input-filtro"
        v-model="store.cerca"
        placeholder="Filtra card per nome"
      />
      <span class="empty" @click="this.store.cerca = ``">X</span>
    </div>
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
.input {
  position: relative;
}
.empty {
  font-weight: bolder;
  color: red;
  position: absolute;
  font-size: 24px;
  top: 15px;
  left: 235px;

  &:hover {
    cursor: pointer;
  }
}
</style>
