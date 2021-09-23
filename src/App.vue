<template>
  <div>
    <Header
     @filterString="genreDigester"
    />
    <Main
      :genreReceived="genreDigested"
     />
   

  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';


export default {
  name: 'App',
  data() {
    return {
      genreDigested: '',
    }
  },
  components: {
    Header,
    Main,
  },
  methods: {
    genreDigester(text) {
      return this.genreDigested = text;
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/general.scss';
body {
  font-family: 'Montserrat';
}
</style>
