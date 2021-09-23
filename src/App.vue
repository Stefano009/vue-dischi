<template>
  <div>
    <Header
     @filterString="genreDigester"
     @filterName="nameDigester"
    />
    <Main
      :genreReceived="genreDigested"
      :nameReceived="nameDigested"
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
      nameDigested: '',
    }
  },
  components: {
    Header,
    Main,
  },
  methods: {
    genreDigester(text) {
      return this.genreDigested = text;
    },
    nameDigester(text) {
      return this.nameDigested = text;
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
