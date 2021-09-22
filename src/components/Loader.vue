<template>
  <div>
      <img src="../assets/img/loader.jpg" alt="">
      <h1>
        Loading ...
      </h1>
  </div>
</template>

<script>
export default {
    name:'Loader',

}
</script>

<style lang="scss" scoped>

div {
    position: fixed;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    padding: 10% 40%;
    background-color: maroon;
    img {
        animation: pulse 2s infinite alternate;
    }
    @keyframes pulse {
        from {
            transform: rotate(-45deg);
            // transform: scale(1);
        }
        to {
            transform: rotate(45deg);
            // transform: scale(0.5);
        }
        
    }
}
</style>>

