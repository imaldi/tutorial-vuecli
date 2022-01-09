<template>
  <div id="app">
    <Header v-on:ganti-hero="gantiHero"></Header>
    <main>
      <p>Hero-hero Terbaik Minggu Ini</p>
      <article>
        <div v-for="(item, index) in heroes" :key="item.id">
          <Hero :hero="item" :index="index"></Hero>
        </div>
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
          nama: "Zilong",
          type: "Fighter",
          gambar: "zilong.jpg",
        },
        {
          id: 3,
          nama: "Aurora",
          type: "Mage",
          gambar: "aurora.jpg",
        },
        {
          id: 4,
          nama: "Zilong",
          type: "Fighter",
          gambar: "zilong.jpg",
        },
        {
          id: 5,
          nama: "Aurora",
          type: "Mage",
          gambar: "aurora.jpg",
        },
        {
          id: 6,
          nama: "Zilong",
          type: "Fighter",
          gambar: "zilong.jpg",
        },
        {
          id: 7,
          nama: "Aurora",
          type: "Mage",
          gambar: "aurora.jpg",
        },{
          id: 8,
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

article {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

main {
  text-align: center;
}
</style>
