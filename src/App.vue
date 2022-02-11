<template>
  <div v-show="!this.Debug.includes('.')">Debug: <a href='/api/text'>API</a> <button @click="this.Debug = 'login'">логин</button><button @click="this.Debug = 'index'">индекс</button><button @click="this.Debug = 'admin'">админ</button><button @click="this.Debug = 'user'">юзер</button></div>
  <custom-header/>
  <login-page v-show="this.Debug.includes('login')"/>
  <index-page v-show="this.Debug.includes('index')"/>
  <admin-account v-show="this.Debug.includes('admin')"/>
  <user-account :requests="UserRequests" v-show="this.Debug.includes('user')"/>
</template>

<script>
import AdminAccount from './components/AdminAccount.vue';
import IndexPage from './components/IndexPage.vue';
import UserAccount from './components/UserAccount.vue';
import CustomHeader from './components/CustomHeader.vue';
import LoginPage from './components/LoginPage.vue';

export default {
  name: 'App',
  components: {
    LoginPage,
    IndexPage,
    AdminAccount,
    UserAccount,
    CustomHeader
  },
  data(){
    return{
      Debug: 'index',
      UserRequests: [],
    }
  },
  created(){
    this.UserRequests = [
      {
        id: 0,
        title: 'Title',
        description: 'description lorem ipsum',
        category: 'testcat',
        photo: 'https://avatars.mds.yandex.net/i?id=06c249e98691b02c219e125bb15cba40-4299853-images-thumbs&n=13',
        photoafter: 'https://avatars.mds.yandex.net/i?id=253379fbfbfd927dc0b90634039d0f64-4859319-images-thumbs&n=13',
        time: '22.8 13:37',
        rstatus: 'new',
      },
      {
        id: 1,
        title: 'Title1',
        description: 'description lorem ipsum1',
        category: 'testcat1',
        photo: 'https://avatars.mds.yandex.net/i?id=889f045ac3a4fc0697eedb1af24ba9c1-5361661-images-thumbs&n=13',
        photoafter: 'https://avatars.mds.yandex.net/i?id=2bdbe315fc852840d01acfa312c83eb1-5521534-images-thumbs&n=13',
        time: '22.8 13:37',
        rstatus: 'new',
      },
      {
        id: 2,
        title: 'Title2',
        description: 'Really long description Really long description Really long description Really long description Really long description Really long description Really long description Really long description Really long description Really long description Really long description Really long description Really long description Really long description Really long description Really long description ',
        category: 'testcat2',
        photo: 'https://avatars.mds.yandex.net/i?id=d5dd9c789c1690c66e17936da8b0ad17-5667262-images-thumbs&n=13',
        photoafter: 'https://avatars.mds.yandex.net/i?id=784988b8b03ce2d41f437afbfb38e597-5911249-images-thumbs&n=13',
        time: '22.8 13:37',
        rstatus: 'new',
      }
    ]
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body{
  margin: 0;
}
</style>
