<template>
    <div class="balanceWrapper">
      <div class="container">
        <h5 class="frutigerColor dollar">$</h5>
        <div v-if="showBalance" class="line"/>
        <h5 v-if="!showBalance" class="frutigerColor balance">{{balance}}</h5>
        <div @click="showBalance = !showBalance" class="imageEye" alt="Sair logo"/>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Balance',
  data() {
    return {
      balance: '19.450',
      showBalance: false,
    }
  },
}
</script>

<style scoped>
  .balanceWrapper {
    flex-grow: 1;
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    align-items: center;
    margin-top: -38px;
    position: relative;
  }

  .imageEye {
    width: 45px;
    height: 45px;
    margin-left: 10px;
    cursor: pointer;
    transition: filter 0.3s ease-in;
    background-size: cover;
    background-repeat: no-repeat;
    background-image: url('../../../assets/images/eye_idle.png');
    transition: filter 0.3s ease-in;
  }

  .imageEye:hover {
    filter: brightness(1.2);
  }

  .imageEye:active {
    background-size: cover;
    background-repeat: no-repeat;
    background-image: url('../../../assets/images/eye_pressed.png');
  }

  .line {
    width: 150px;
    height: 2px;
    background: linear-gradient(to bottom, #ffe773, #ffcb00, #ffad00);
    border: 2px solid black;
  }

  .container {
    position: absolute;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: right;
    align-items: center;
    margin-right: 50px;
  }

  .dollar {
    margin-top: 5px;
  }

  .balance {
    width: 154px;
    font-size: 30px;
    margin-top: 55px;
  }

</style>