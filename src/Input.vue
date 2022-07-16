<template>
    <div>
        <input type="text" v-bind:value="msg" v-on:input="changeMessage"></input>
        <p> {{ message }}</p>
    </div>
</template>


<script>
    export default {
        props: [
            'msg'
        ],
        data() {
            return {
                message: ''
            }
        },
        methods: {
            changeMessage(event) {
                this.message = event.target.value;
                this.$emit('messageChanged', this.message);
                // $ is built in method
            }
        }
    }
</script>