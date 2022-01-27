<template>
  <div class="requestroot">
        <div class="topbar">
            <h3 class="tptext">#{{request.id}}</h3>
            <h3 class="tptext">{{request.title}}</h3>
            <h3 class="tptext">{{request.time}}</h3>
        </div>
        <div class="secondBar">
            <div><h3 class="sbcont">Категория: {{request.category}}</h3></div>
            <div><h3 class="sbcont">Статус: {{request.rstatus}}</h3></div>
        </div>
        <div class="body">
            <div><img :src="request.photo" alt=""></div>
            <p>{{request.description}}</p>
        </div>
  </div>
</template>

<script>
export default {
  name: 'Request',
  components: {
  },
  props:{
      request: Object,
  },
}
</script>

<style scoped>
    .topbar{
        background: lightblue;
        text-align: left;
        border-radius: 5px 5px 0px 0px;
        padding: 4px;
        display: flex;
        justify-content: space-between;
    }
    .requestroot{
        position: parent;
        border: solid blue 1px;
        border-radius: 5px;
        min-width: 480px;
        width: 50%;
    }
    img{
        margin: 5px;
        height: 100px;
        width: 100px;
        background: lightblue;
    }
    .secondBar{
        display: flex;
        align-content: center;
        flex-wrap: nowrap;
        flex-direction: row;
        align-items: flex-start;
        justify-content: flex-start;
    }
    .sbcont{
        margin-top: 3px;
        margin-right: 15px;
        margin-bottom: 5px;
    }
    .body{
        display: flex;
    }
        h3{
        margin: 0;
    }
</style>