<template>
    <input :type="this.type" :value="this.text">
</template>

<script>

export default {
  name: 'CustomButton',
  components: {
  },
  props:{
      text: {
            type: String,
            default: 'button',
      },
      type: {
            type: String,
            default: 'button',
      },
  },
}
</script>

<style scoped>
    input{
        height: 40px;
        width: auto;
        border: solid #0000FF 1px;
        border-radius: 5px;
        color: white;
        font-size: 100%;
        padding: 0px 25px;
        background-color: #0000FF;
    }
    input:hover{
        background-color: #4444FF;
    }
    input:active{
        background-color: #6666FF;
    }
</style>
