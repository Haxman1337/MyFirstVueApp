<template>
    <form action="" @submit="onSubmit">
        <div>
            <CustomInput ref="input1" type="text" placeholder="Логин" pattern="[^]+" errormsg="Поле не должно быть пустым"/>
            <br>
            <CustomInput ref="input2" type="password" :passshow="true" placeholder="Пароль" pattern="[^]+" errormsg="Поле не должно быть пустым"/>
            <div><input type="checkbox" name="remember"> <label for="remember">Запомнить меня</label></div>
            <br>
        </div>
        <custom-button text="Войти" type="submit"/>
    </form>
</template>

<script>
import CustomButton from './CustomButton.vue';
import CustomInput from './CustomInput.vue';
export default {
    name: 'LoginForm',
    data() {
        return {
        }
    },
     
     components: {
        CustomInput,
        CustomButton,
    },
    methods:{
        onSubmit(event) {
            var a = false;

            if (this.$refs['input1'].hasError()) a = true;
            if (this.$refs['input2'].hasError()) a = true;

            console.log(a);

            if (a) {
                event.preventDefault();
            }
            else console.log("submit");
            
        },
        inputError(a) {
            this.inputErrorVar = a;
        }
    }
}
</script>

<style scoped>

</style>
