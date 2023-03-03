<template>
  <main>
    <div class="container">
      <select name="cianuro" id="">
        <option selected>Open this select menu</option>
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
      </select>
    </div>
    <div class="container box">
      <div class="result-info">
        <h3>Trovate 41 card</h3>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
select {
  width: 200px;
  height: 30px;
  margin: 30px 10px;
}
.container.box {
  background-color: aqua;
  padding: 50px;
  color: black;
  .result-info {
    color: white;
    background-color: black;
    line-height: 2rem;
    padding: 20px 10px;
  }
}
</style>
