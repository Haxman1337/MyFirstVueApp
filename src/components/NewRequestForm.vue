<template>
  <div class="formroot">
      <form action="#">
          <custom-input placeholder="Название заявки" pattern="[^]+$"/>
          <custom-input placeholder="Категория" pattern="[^]+$"/>
          <custom-text-area placeholder="Описание заявки"/>
          <input type="file" name="" class="infile">
          <custom-button type="submit" @click="addReqClick" text="Отправить"/>
      </form>
  </div>
</template>

<script>
import CustomButton from './CustomButton.vue'
import CustomInput from './CustomInput.vue'
import CustomTextArea from './CustomTextArea.vue';
export default {
  name: 'NewRequestForm',
  components: {
    CustomInput,
    CustomButton,
    CustomTextArea
  },
  methods:{
      addReqClick(e){
          e.preventDefault();
      },
  }
}
</script>

<style scoped>
    .formroot{
        padding-top: 10px;
        padding-bottom: 10px;
        background: lightgray;
        border-top: solid transparent;
        border-bottom: solid transparent;
        border-color: grey;
        фborder-image: linear-gradient(45deg, red , yellow);
        фborder-image-slice: 1;
    }
    form{
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
        align-content: center;
        justify-content: center;
        align-items: center;
    }
    .infile{
        margin: 10px 0;
    }
</style>