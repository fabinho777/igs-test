<template>
    <div class="jackpotWrapper">
        <h5 class="frutigerColor jackpotTitle">JACKPOT</h5>
      <div class="jackpotValueWrapper">
        <h6 class="frutigerColor dollar">$</h6>
        <h2 class="frutigerColor jackpotBalance">{{jackpot}}</h2>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Jackpot',
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
  .jackpotWrapper {
    flex-grow: 1;
    position: relative;
    display: flex;
    flex-direction: column;
  }

  .jackpotTitle {
    font-size: 30px;
    font-weight: 900;
    margin: 0;
    margin-top: -2px;
  }

  .jackpotBalance {
    margin: 0;
    font-size: 75px;
    font-weight: 900;
    margin-top: -10px;
  }

  .jackpotValueWrapper {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: center;
    align-items: center;
  }
</style>