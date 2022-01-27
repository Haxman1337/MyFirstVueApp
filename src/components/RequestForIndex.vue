<template>
    <div class="root">
        <div class="body" :style="cssProps">
            <h3>{{cat}}: {{title}} - {{time}}</h3>
            <div class="imagebox"></div>
        </div>
    </div>  
</template>

<script>
export default {
  name: 'RequestForIndex',
  data(){
      return{
      }
  },
  components: {
      
  },
  props:{
      img: String,
      imgafter: String,
      title: String,
      time: String,
      cat: String,
  },
  methods:{
  },
    computed: {
    cssProps() {
      return {
        '--img': 'url('+(this.img)+')',
        '--imgafter': 'url('+(this.imgafter)+')',
      }
    },
    }
}
</script>

<style scoped>
    .body{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-content: center;
        flex-wrap: wrap;
        align-items: center;
    }
    .imagebox{
        margin: 5px;
        height: 40vh;
        width: 40vh;
        background: lightblue var(--imgafter) no-repeat;
        background-size: cover;
        border: solid blue 1px;
        border-radius: 50px;
    }
    .imagebox:hover{
        background: blue var(--img) no-repeat;
        background-size: cover;
    }
</style>