<template>
  <section class="container-fluid">
      <div class="row">
          <div class="col-6 col-md-4 col-xl-2">
              
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios'
export default {
    name:'Main',
    data() {
        return {
            APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            albums: [],

        }
    },
    created() {
        this.getAlbums();
    },
    methods: {
        getAlbums() {

            axios
            .get(this.APIUrl)
            .then (res => {
                // console.log(res.data)
                this.albums = res.data.response
            })
        }
    }

}
</script>

<style lang="scss" scoped>
@import '../assets/style/general.scss';
section {
    background-color: $darkerGray;
    height: calc(100vh - 60px);
}
</style>