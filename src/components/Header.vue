<template>
  <header>
    <img class="m-1" src="../assets/img/spotify.png" alt="spotify icon">
    <div class="selectors">
      <select @change="$emit('filterString', selected)" v-model="selected">
        <option  v-for="(genre , index) in genres" :key="index" :value="genre.value">{{genre.value}}</option>
      </select>
      <select @change="$emit('filterName', selectedName)" v-model="selectedName">
        <option  v-for="(bandName , index) in bandNames" :key="index" :value="bandName.value">{{bandName.value}}</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      selected:'',
      selectedName: '',
      bandNames:[
        {
          value: ''
        },
        {
        value: 'Bon Jovi'
        },
        {
        value: 'Queen'
        },
        {
        value: 'Sting'
        },
        {
        value: 'Steve Gadd Band'
        },
        {
        value: 'Iron Maiden'
        },
        {
        value: 'Eric Clapton'
        },
        {
        value: 'Deep Purple'
        },
        {
        value: 'Metallica'
        },
        {
        value: 'Dave Weckl'
        },
        {
        value: 'Michael Jacjson'
      }
      ],
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
    select {
      margin:0 10px;
    }
  }
}
</style>
