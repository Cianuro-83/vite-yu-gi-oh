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
        <img src="../assets/gif_animate_yu-gi-oh10.gif" alt="" />
        <h3>Trovate 41 card</h3>
        <img src="../assets/gif_animate_yu-gi-oh10.gif" alt="" />
      </div>
      <div class="card">
        <ul class="grid">
          <Card v-for="(el, i) in cards" :key="el.id" :card="el" />
        </ul>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import Card from "./Card.vue";
export default {
  components: {
    Card,
  },
  data() {
    return {
      cards: [],
      //********************
      // FINE RETURN
    };
    // FINE DATA
  },
  //******************** */
  methods: {
    prendiCard() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then((res) => {
          console.log(res);
          console.log(res.data);
          console.log(res.data.data);
          this.cards = res.data.data;
          console.log(this.cards);
        });
    },
    //********************
    // FINE METHODS
  },
  //******************** */
  created() {
    this.prendiCard();
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
  background-image: url(../assets/tumblr_ntahc6bHBL1uue2e4o1_500.gif);
  // background-repeat: no-repeat;
  // background-size: cover;
  // background-position: top;
  padding: 50px;
  color: black;
  .result-info {
    color: white;
    background-color: rgba(234, 169, 18, 0.9);
    display: flex;
    align-items: center;
    justify-content: space-between;
    line-height: 2rem;
    padding: 20px 10px;
  }
  img {
    width: 400px;
  }
}
.grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 40px;
}
</style>
