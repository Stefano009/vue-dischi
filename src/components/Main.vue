<template>
  <section>
      <div v-if="!loading" class="container-fluid d-flex flex-column align-items-center justify-content-center">
            <div  class="row d-flex align-items-center justify-content-center" v-for=" i in Math.ceil(albums.length / 5 )" :key="i" >
                <div v-for="(disk, i) in albums.slice((i - 1) * 5, i * 5)" :key="i" class="col-2 mx-2">
                    <Disk 
                        :diskInfo="disk"
                    />
                </div>
            </div>
      </div>

       <Loader v-else />
  </section>
</template>

<script>
import axios from 'axios';
import Disk from './Disk';
import Loader from './Loader.vue';

export default {
    name:'Main',
    components: {
        Disk,
        Loader,        
    },
    data() {
        return {
            APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            albums: [],
            loading: true,

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
                    this.loading = false;
                    //timeout to verify that everything works
                    // setTimeout( () => {this.loading = false; }, 5000);
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