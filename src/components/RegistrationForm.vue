<template>
    <form action="" @submit="onSubmit">
        <div>
            <CustomInput ref="input1" type="text" placeholder="ФИО" pattern="^[А-Яа-я\- ]+$" errormsg="Допустимые символы: кириллица, дефис и пробел"/>
            <br>
            <CustomInput ref="input2" type="text" placeholder="Логин" pattern="^[A-z0-9]+$" errormsg="Допустимые символы: латиница и цифры"/>
            <br>
            <CustomInput ref="input3" type="text" placeholder="E-mail" pattern="^[a-z0-9]+@[a-z]+\.[a-z]+$" errormsg="Это не валидный e-mail"/>
            <br>
            <double-password ref="input4"/>
            <div class="cb"><input type="checkbox" name="agree" v-model="this.cbchecked"> <label for="agree">Соглашаюсь с <a href="">Условиями Использования</a></label></div>
            <p v-show="this.cberr">Для продолжения согласитесь</p>
            <br>
        </div>
        <custom-button text="Зарегистрироваться" type="submit"/>
    </form>
</template>

<script>
import CustomButton from './CustomButton.vue';
import CustomInput from './CustomInput.vue';
import DoublePassword from './DoublePassword.vue';
export default {
    name: 'RegistrationForm',
    data() {
        return {
            cberr: false,
            cbchecked: false,
        }
    },
     
     components: {
        CustomInput,
        CustomButton,
          DoublePassword,
    },
    methods:{
        onSubmit(event) {
            var a = false;

            if (this.$refs['input1'].hasError()) a = true;
            if (this.$refs['input2'].hasError()) a = true;
            if (this.$refs['input3'].hasError()) a = true;
            if (this.$refs['input4'].hasError()) a = true;
            console.log(a);
            if (!this.cbchecked) {a = true; this.cberr = true} else {this.cberr = false;}

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
p{
    color: red;
    font-size: .75rem;
    margin-top: 5px;
}
.cb{
    margin: 0 10%;
}
</style>
