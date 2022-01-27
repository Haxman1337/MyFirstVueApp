<template>
  <div class="formroot">
      <form action="#">
          <custom-input placeholder="Название заявки" ref="input1" pattern="[^]+$"/>
          <custom-input placeholder="Категория" ref="input2" pattern="[^]+$"/>
          <custom-text-area placeholder="Описание заявки" ref="input3"/>
          <div><custom-button @click="this.$refs['input4'].click()" :text='btnText' class='upbtn'/> : {{this.uploadedFile}}</div>
          <input type="file" name="uplimg" class="infile" ref="input4" accept="image/*" @change="fileChange($event.target.files)">
          <p>{{this.uploadError}}</p>
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
  data(){
      return{
          uploadError: '',
          uploadedFile: 'Не загружено',
          btnText: 'Загрузить фото',
      }
  },
  components: {
    CustomInput,
    CustomButton,
    CustomTextArea
  },
  methods:{
      addReqClick(e){
          var a = false;

          if(this.$refs['input1'].hasError()) a = true;
          if(this.$refs['input2'].hasError()) a = true;
          //if(this.$refs['input3'].hasError()) a = true;
          if(this.$refs['input4'].files.length == 0) {a = true; this.uploadError = 'Загрузите фото'; }

          if(a)e.preventDefault();
          else{
              this.uploadError = '';
          }
      },
      fileChange(files){
          if(files.length == 0) {this.uploadedFile = 'Не загружено'; this.btnText = 'Загрузить фото';}
          else {this.uploadedFile = files[0].name; this.btnText = 'Фото загружено'; this.uploadError = '';}
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
        margin: 10px 0 0 0;
        display: none;
    }
    p {
    color: red;
    font-size: .75rem;
    margin-top: 5px;
    }

</style>