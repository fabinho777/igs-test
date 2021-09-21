<template>
  <div class="optionsWrapper">
      <div class="image imageLogout" alt="Sair logo"/>
      <div class="image imageHelp" alt="Ajuda logo"/>
  </div>
</template>

<script>
export default {
  name: 'Options',
}
</script>

<style scoped>
  .optionsWrapper {
    flex-grow: 1;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    padding-top: 10px;
    position: relative;
  }

  .imageLogout {
    background-size: cover;
    background-repeat: no-repeat;
    background-image: url('../../../assets/images/logout_idle.png');
    margin-left: 20px;
  }

  .imageHelp {
    background-size: cover;
    background-repeat: no-repeat;
    background-image: url('../../../assets/images/help_idle.png');
    margin-left: 90px;
  }

  .imageLogout:active {
    background-size: cover;
    background-repeat: no-repeat;
    background-image: url('../../../assets/images/logout_pressed.png');
  }

  .imageHelp:active {
    background-size: cover;
    background-repeat: no-repeat;
    background-image: url('../../../assets/images/help_pressed.png');
  }
</style>