<template>
<tab-control tab1name="Вход" tab2name="Регистрация" class="tc">
    <template v-slot:page1>
        <login-form/>
    </template>
    <template v-slot:page2>
        <registration-form/>
    </template>
</tab-control>
</template>

<script>
import TabControl from './TabControl.vue';
import LoginForm from './LoginForm.vue';
import RegistrationForm from './RegistrationForm.vue';
export default {
  name: 'LoginPage',
  components: {
    TabControl,
    LoginForm,
    RegistrationForm
  }
}
</script>

<style scoped>
.tc{
    max-width: 30%;
    min-width: 300px;
    display: inline-block;
}
</style>
