<template>
    <custom-button class="btn" :text="addBtnText" @click="addBtnClick"/>
    <new-request-form v-show="showNewReq" class="form"/>
    <h2>Ваши заявки:</h2>
    <request class="req" v-for="r in requests" :key="r.id" :request="r"/>
</template>

<script>
import Request from './Request.vue'
import CustomButton from './CustomButton.vue'
import NewRequestForm from './NewRequestForm.vue'
export default {
  name: 'RequestsTracker',
  data(){
      return{
          showNewReq: false,
          addBtnText: 'Добавить новую заявку',
      }
  },
  components: {
    Request,
    CustomButton,
    NewRequestForm,
  },
  props:{
      requests: Array,
  },
  methods:{
      addBtnClick(){
          if(this.showNewReq) this.addBtnText = 'Добавить новую заявку';
          else this.addBtnText = 'Скрыть';
          this.showNewReq = !this.showNewReq;
      },
  },
}
</script>

<style scoped>
    .req{
        margin: 0 auto;
        margin-bottom: 10px;
    }
    .btn{
        margin: 5px;
    }
    .form{
        opacity: 0;
        animation: ani .8s forwards;
    }
    @keyframes ani {
        0% {opacity: 0;}
        100% {opacity: 1;}
    }
</style>