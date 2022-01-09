<template>
  <div id="app">
    
    <Header></Header>
    <main>
      <ul>
        <li>
          <img :src="gambar">
          <p>{{ hero.nama }}</p>
          <p>Jenis Hero: <em>{{ hero.type }}</em></p>
        </li>
      </ul>
    </main>
    <Footer></Footer>
    
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
export default {
  name: "App",
  components: {
    Header,
    Footer,
  },
  data: function () {
    return {
      hero: {
        nama: "Aurora",
        type: "Mage",
        gambar: "aurora.jpg",
      },
    };
  },
  methods: {
    gantiHero: function () {
      this.hero.nama = "Zilong"
      this.hero.type = "Fighter"
      this.hero.gambar = "zilong.jpg"
    },
  },
  computed: {
    gambar: function(){
      return require('./assets/hero/' + this.hero.gambar)
    }
  }
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
  border: 1px solid #ccc
}
</style>
