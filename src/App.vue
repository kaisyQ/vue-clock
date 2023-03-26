<template>
  <MainWrapper />
</template>

<script>
import MainWrapper from './components/MainWrapper.vue'

export default {
  name: 'App',
  components: {
    MainWrapper
  }
}
</script>
<style>
@font-face {
  font-family: "Gotham Pro";
  src: url("./assets/fonts/GothamPro/gothampro.ttf");
}

  *,*::before,*::after {
    box-sizing: border-box;
    padding: 0;
    margin: 0;
  }

  html {
    font-size: 62.5%;
  }


  body {

    font-family: 'Gotham Pro', sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 2.2rem;
    line-height: 2.1rem;
    text-align: center;
    color: #9E9E9E;

    
    height: 100vh;
    
    margin-top: 7.2rem;

    background: #353638;
  }

</style>
