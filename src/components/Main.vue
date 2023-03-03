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
      <div class="card">
        <ul class="grid">
          <li v-for="card in cards" :key="card.id">
            <img :src="card.card_images[0].image_url" alt="" class="thumb" />
            <h3 class="name">{{ card.name }}</h3>
            <p>{{ card.archetype }}</p>
          </li>
        </ul>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
export default {
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
          console.log(this.card);
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
  background-color: rgb(143, 139, 31);
  padding: 50px;
  color: black;
  .result-info {
    color: white;
    background-color: black;
    line-height: 2rem;
    padding: 20px 10px;
  }
}
.grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 40px;
}
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
