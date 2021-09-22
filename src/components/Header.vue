<template>
  <header>
    <img class="m-1" src="../assets/img/spotify.png" alt="spotify icon">
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../assets/style/general.scss';

header{
  background-color: $lighterGray;
  height: 60px;
  
  img{
    height: 50px;
  }
}
</style>
