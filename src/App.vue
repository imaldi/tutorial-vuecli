<template>
  <div id="app">
    <Header v-on:ganti-hero="gantiHero"></Header>
    <main>
      <div v-for="item in heroes" :key="item.id">
        <Hero v-bind:hero="item"></Hero>
      </div>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Hero from "./components/Hero.vue";

export default {
  name: "App",
  components: {
    Header,
    Footer,
    Hero,
  },
  data: function () {
    return {
      heroes: [
        {
          id: 1,
          nama: "Aurora",
          type: "Mage",
          gambar: "aurora.jpg",
        },
        {
          id: 2,
          nama: "Zilong",
          type: "Fighter",
          gambar: "zilong.jpg",
        },
      ],
    };
  },
  methods: {
    gantiHero: function () {
      this.hero.nama = "Zilong";
      this.hero.type = "Fighter";
      this.hero.gambar = "zilong.jpg";
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}

main img {
  width: 80px;
  border: 1px solid #ccc;
}
</style>
