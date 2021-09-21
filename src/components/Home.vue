<template>
    <div class="homeWrapper">
        <Header v-bind:jackpot="jackpot"/>
        <Content @changeJackpot="changeJackpot"/>
        <Footer/>
    </div>
</template>

<script>
import Footer from './Footer/Footer.vue'
import Content from './Content/Content.vue'
import Header from './Header/Header.vue'

export default {
  name: 'Home',
  components: {
    Header,
    Content,
    Footer
  },
data() {
    return {
      jackpot: '0'
    }
  },
  methods: {
    changeJackpot(item) {
      this.jackpot = item;
    }
  }
}
</script>

<style scoped>
  .homeWrapper {
    display: flex;
    flex-direction: column;
    background-size: cover;
    background-repeat: no-repeat;
    background-image: url('../assets/images/background.png');
    height: 100vh;
  }
</style>