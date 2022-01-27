<template>
  <div>
    <h1>Добро пожаловать в систему приема заявок "Whatever"</h1>
    <h2>Обработано заявок: [Number]</h2>
    <h2>Последняя решенная проблема:</h2>
    <request-for-index title="Мусор, грязь" cat="Облагораживание" time="22.08.20 13:37" :img='this.i' :imgafter='this.ia'/>
    <br>
    <h3>Для работы с сайтом <a href="#">авторизуйтесь</a></h3>
  </div>
</template>

<script>
import RequestForIndex from './RequestForIndex.vue';

export default {
  name: 'IndexPage',
  data(){
    return{
      i: 'https://indicator.ru/thumb/1500x0/imgs/2019/08/20/12/3524307/b74d0e65a9b781ebb779bd6021e5fdde3d047b93.jpg',
      ia: 'https://dynamic-media-cdn.tripadvisor.com/media/photo-o/10/a3/01/9e/img-20170611-220124-085.jpg?w=700&h=500&s=1',
    }
  },
  components: {
    RequestForIndex,
  }
}
</script>

<style>
</style>