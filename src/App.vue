<template>
  <!--<img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <Home/>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style>
  body {
    padding: 0;
    margin: 0;
  }

  @font-face {
    font-family: 'Frutiger';
    src: url('./assets/fonts/FrutigerLTStd-Black.woff') format('woff');
    font-weight: normal;
  }

  #app {
    font-family: Frutiger;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin: 0;
  }

  .frutigerColor {
    background-image: linear-gradient(to bottom, #ffe773, #ffcb00, #ffad00);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    color: black;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #000;
  }

  .dollar {
    margin: 0;
    font-size: 30px;
    font-weight: 900;
    margin-top: -20px;
    margin-right: 10px;
  }

  .image {
    width: 60px;
    height: 60px;
    cursor: pointer;
    transition: filter 0.3s ease-in;
    position: absolute;
  }

  .image:hover {
    filter: brightness(1.2);
  }

</style>
