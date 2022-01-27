<template>
    <div>
        <CustomInput v-model="pass1" ref="input1" type="password" :passshow="true" placeholder="Пароль" pattern="[^]+" errormsg="Поле не должно быть пустым" />
        <br>
        <CustomInput v-model="pass2" ref="input2" type="password" :passshow="true" placeholder="Повторите пароль" pattern="[^]+" errormsg="Поле не должно быть пустым" />
        <p>{{error}}</p>
    </div>
</template>

<script>
import CustomInput from './CustomInput.vue'
export default {
    components: { CustomInput },
    name: 'DoublePassword',
    data() {
        return {
            pass1: '',
            pass2: '',
            error: '',
        }
    },
    props: {

    },
    watch: {

    },
    methods:{
        hasError(){
            var a = false;
            if (this.$refs['input1'].hasError()) a = true;
            if (this.$refs['input2'].hasError()) a = true;
            if (this.pass1 != this.pass2) {this.error = 'Пароли не совпадают'; a = true;}
            if (!a) {this.error = ''; return false;}
            else return true;
        },
    },
}
</script>

<style scoped>
p{
    color: red;
    font-size: .75rem;
    margin-top: 0px;
}
</style>
