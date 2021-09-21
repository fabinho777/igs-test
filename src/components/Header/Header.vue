<template>
    <div class="headerWrapper">
        <Options/>
        <Jackpot v-bind:jackpot="jackpot"/>
        <Balance/>
    </div>
</template>

<script>
import Balance from './parts/Balance.vue'
import Options from './parts/Options.vue'
import Jackpot from './parts/Jackpot.vue'

export default {
  name: 'Header',
  components: {
    Balance,
    Options,
    Jackpot
  },
  props: {
   jackpot: {
    type: String,
    required: false,
    default: '0'
   }
  }
}
</script>

<style scoped>
  .headerWrapper {
    background-image: url('../../assets/images/header.png');
    background-repeat: no-repeat;
    background-size: 100% 120px;
    width: 100%;
    height: 120px;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
  }
</style>