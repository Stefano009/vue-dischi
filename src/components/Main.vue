<template>
  <section class="container-fluid d-flex flex-column align-items-center justify-content-center">
      <div class="row d-flex align-items-center justify-content-center" v-for=" i in Math.ceil(albums.length / 5 )" :key="i" >
          <div v-for="(disk, i) in albums.slice((i - 1) * 5, i * 5)" :key="i" class="col-2">
              <Disk 
                :diskInfo="disk"
              />
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';
import Disk from './Disk';
export default {
    name:'Main',
    components: {
        Disk,
    },
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
    height: calc(100vh - 40px);
    width: 100%;
    .row {
        width: 70%;
        margin: 0 auto;
    }
}

</style>