<template>
  <div id="app">
    <Header v-on:ganti-hero="gantiHero"></Header>
    <main>
      <p>Hero-hero Terbaik Minggu Ini</p>
      <!-- <img   :src="gambar"/> -->
      <article v-if="!selectedHero">
        <div v-for="(item, index) in heroes" :key="item.id">
          <Hero :hero="item" :index="index"></Hero>
        </div>
      </article>
      <article v-else>
          <Hero :hero="selectedHero" :index="0"></Hero>
      </article>
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
          nama: "Akai",
          type: "Tank",
          gambar: "akai.jpg",
        },
        {
          id: 3,
          nama: "Bruno",
          type: "Marksman",
          gambar: "bruno.jpg",
        },
        {
          id: 4,
          nama: "Gatotkaca",
          type: "Fighter",
          gambar: "gatotkaca.png",
        },
        {
          id: 5,
          nama: "Hilda",
          type: "Fighter",
          gambar: "hilda.jpg",
        },
        {
          id: 6,
          nama: "Lancelot",
          type: "Assasin",
          gambar: "lancelot.jpg",
        },
        {
          id: 7,
          nama: "Lapu lapu",
          type: "Figter",
          gambar: "lapulapu.jpg",
        },{
          id: 8,
          nama: "Zilong",
          type: "Fighter",
          gambar: "zilong.jpg",
        },
      ],
      selectedHero: '',
    };
  },
  methods: {
    gantiHero: function () {
      this.selectedHero = this.randomHero()

    },
    randomHero(){
      return this.heroes[Math.floor(Math.random() * this.heroes.length)]
    }
  },
  // computed: {
  //   gambar: function () {
  //     return require("./assets/hero/" + this.selectedHero);
  //   },
  // },
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

article {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

main {
  text-align: center;
}
</style>
