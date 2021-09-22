<template>
  <div class="d-flex flex-column text-center">
      <img :src="diskInfo.poster" :alt="diskInfo.title + diskInfo.author">
      <h2>
          {{diskInfo.title}}
      </h2>
      <span>
          {{diskInfo.author}}
      </span>
      <span>
          {{diskInfo.year}}
      </span>
  </div>
</template>

<script>
export default {
    name:'Disk',
    props: ['diskInfo']

}
</script>

<style lang="scss" scoped>
@import '../assets/style/general.scss';

div {
    background-color: $lighterGray;
    color: #808080;
    min-height: 210px;
    min-width: 115px;
    font-size: .6rem;
    margin: 5px 10px;
}
h2 {
    color: white;
    font-size: 1rem;
    font-weight: 700;

}
img {
    padding: 10px;
    object-fit: cover;
}
</style>>
