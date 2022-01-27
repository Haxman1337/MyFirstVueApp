<template>
    <div class="window">  
        <div class="tab-section">
            <div class="tab-button tab-button-left" @click="tab1Click" :class="{tabActive : selectedTab == 0}">{{tab1name}}</div><div class="tab-button tab-button-right" @click="tab2Click" :class="{tabActive : selectedTab == 1}">{{tab2name}}</div>
        </div>
        <div class="content content1" v-show="this.selectedTab == 0"><slot name="page1"></slot></div>
        <div class="content content2" v-show="this.selectedTab == 1"><slot name="page2"></slot></div>
    </div>

</template>

<script>
export default {
  name: 'TabControl',
  data(){
    return{
        selectedTab: 0,
    }  
  },
  components: {
  },
  props:{
      tab1name: '',
      tab2name: '',
  },
  methods:{
      tab1Click(){
            this.selectedTab = 0;
      },
      tab2Click(){
            this.selectedTab = 1;
      }
  }
}
</script>

<style scoped>
.tab-button{
    width: 50%;
    background-color: rgb(194, 194, 194);
    padding: 10px;
    user-select: none;
}
.tab-button-left{
    border-radius: 10px 0px 0px 0px;
}
.tab-button-right{
    border-radius: 0px 10px 0px 0px;
}
.tab-section{
    display: flex;
    flex-direction: row;
}
.tabActive{
    background-color: rgb(255, 255, 255);
}
.content{
    padding: 25px 0;
}
.window{
    border: solid 1px black;
    border-radius: 10px;
    background-color: white;
}
</style>
