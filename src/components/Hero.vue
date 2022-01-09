<template>
    <ul>
        <li>
          <img :src="gambar">
          <p>{{ hero.nama }}</p>
          <p>Jenis Hero: <em>{{ hero.type }}</em></p>
        </li>
    </ul>
</template>
<script>
export default {
    props: ['hero'],
    computed: {
    gambar: function(){
      return require('../assets/hero/' + this.hero.gambar)
    }
  }
}
</script>

<style scoped>

</style>