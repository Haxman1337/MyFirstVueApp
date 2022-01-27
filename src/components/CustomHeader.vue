<template>
  <header class="root">
    <img src="../assets/logo.png" alt="">
    <custom-button class="cb" text="Выход"/>
  </header>
</template>

<script>
import CustomButton from './CustomButton.vue'
export default {
  name: 'CustomHeader',
  components: {
    CustomButton
  },
}
</script>

<style scoped>
    .root{
        width: 100%;
        height: 60px;
        background: lightblue;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-content: space-between;
        justify-content: space-between;
    }
    img{
      height: 60px;
      width: 60px;
      margin: 0 0 0 3px;
    }
    .cb{
      margin: 8px;
    }
</style>