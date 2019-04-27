<template>
    <form @submit.prevent="">
        <input type="email" v-model="email">
        <button @click="enter()"> Zaloguj </button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                email: ''
            }
        },
        methods: {
            enter() {
                this.$emit('login', this.email);
            }
        }
    }
</script>