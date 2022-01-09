<template>
    <header>
      <img alt="Vue logo" src="../assets/logo.png" />
      <h3>Mobile Legends Bang Bang</h3>
      <button v-on:click="$emit('ganti-hero')">Ganti Hero</button>
    </header>
</template>
<script>
export default{
    methods: {
        gantiHero:function(){
            
        }
    }
}
</script>
<style scoped>

</style>