<template>
  <header>
    <img class="m-1" src="../assets/img/spotify.png" alt="spotify icon">
    <div class="selectors">
      <select @change="$emit('filterString', selected)" v-model="selected">
        <option  v-for="(genre , index) in genres" :key="index" :value="genre.value">{{genre.value}}</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      selected:'Filtra per genere',
      genres: [
        {
          value: ''
        },
        {
          value: 'Rock'
        },
        {
          value: 'Metal'
        },
        {
          value: 'Pop'
        },
        {
          value: 'Jazz'
        },
      ]
    }
  },

  // methods:{
  //   filterString() {
  //     console.log(this.selected);
  //     return this.$emit('selectGenre', this.selected)
  //   }
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../assets/style/general.scss';

header{
  background-color: $lighterGray;
  height: 40px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 15px;
  
  img{
    height: 35px;
  }
  .selectors {
    margin:0 15px;
    font-size: .6rem;
  }
}
</style>
