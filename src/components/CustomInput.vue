<template>
    <div class="CustomInputRoot">
    
        <div class="inputBase"><input :type="this.inputtype" :placeholder="placeholder" @input="$emit('update:modelValue', $event.target.value)" v-model="text" name="text"><i v-show="this.passshow" @click="showPassToggle" ref="vis" :class="passtoggled ? 'novis' : 'vis'"></i></div>
    
        <p>{{error}}</p>
    
    </div>
</template>

<script>
export default {
    name: 'CustomInput',
    data() {
        return {
            text: '',
            error: null,
            passtoggled: false,
            inputtype: this.type,
        }
    },
    props: {
        type: {
            type: String,
            default: 'text',
        },
        placeholder: {
            type: String,
            default: '',
        },
        pattern: {
            type: String,
            default: null,
        },
        errormsg: {
            type: String,
            default: 'Введенные данные не соответствуют требованиям',
        },
        passshow: {
            type: Boolean,
            default: false,
        },
    },
    methods: {
        checkInput() {
            if (this.pattern !== null && this.pattern !== '') {
                if (this.text.length != 0) {
                    var r = RegExp(this.pattern);
                    if (!r.test(this.text)) {
                        this.error = this.errormsg;
                    } else {
                        this.error = '';
                    }
                } else {
                    this.error = 'Поле не должно быть пустым';
                }

            }
        },
        hasError() {
            this.checkInput()
            if (this.error !== null && this.error == '') {
                return false;
            }
            return true;
        },
        showPassToggle() {
            let $ref = this.$refs['vis']
            if (!this.passtoggled) { this.inputtype = 'text'; } else { this.inputtype = 'password'; }
            this.passtoggled = !this.passtoggled
        },
    },
    watch: {
        text: function() { this.checkInput() },
    },
}
</script>

<style scoped>
p {
    color: red;
    font-size: .75rem;
    margin-top: 5px;
}

.CustomInputRoot {
    width: 200px;
    display: inline-flex;
    flex-direction: column;
    align-content: center;
    justify-content: center;
    align-items: stretch;
}

input {
    height: 25px;
    font-size: 1.2em;
    border-radius: 5px;
    border: solid 1px rgb(0, 0, 255);
    width: 100%;
}

input:focus {
    outline: none;
    border: solid 1px rgb(0, 122, 0);
}

i {
    position: absolute;
    top: 1px;
    right: -5px;
    display: inline-block;
    width: 27px;
    height: 27px;
    background: white;
    border-radius: 5px;
    z-index: 1;
}

.inputBase {
    position: relative;
}

.vis {
    background: url('../assets/visibility.png') no-repeat white;
    background-position: center;
}

.novis {
    background: url('../assets/visibility_off.png') no-repeat white;
    background-position: center;
}
</style>
