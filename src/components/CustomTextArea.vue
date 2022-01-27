<template>
    <div>
        <textarea name="this.tbname" cols="30" rows="10" :placeholder="placeholder"></textarea>
    </div>
</template>

<script>
    export default {
        name: 'CustomTextArea',
        props: {
            tbname: String,
            placeholder: String,
        },

}
</script>

<style scoped>
    textarea {
    font-size: 1.2em;
    border-radius: 5px;
    border: solid 1px rgb(0, 0, 255);
    width: 100%;
    }

    textarea:focus {
    outline: none;
    border: solid 1px rgb(0, 122, 0);
    }
</style>