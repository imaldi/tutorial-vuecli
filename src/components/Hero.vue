<template>
  <ul>
    <li>
      <img :src="gambar" />
      <p>{{ index + 1 }} - {{ hero.nama }}</p>
      <p>
        Jenis Hero: <em>{{ hero.type }}</em>
      </p>
    </li>
  </ul>
</template>
<script>
export default {
  props: ["hero", "index"],
  computed: {
    gambar: function () {
      return require("../assets/hero/" + this.hero.gambar);
    },
  },
};
</script>

<style scoped>
p {
  /* color: salmon */
  margin: 0;
}
li {
  list-style: none;
}
</style>