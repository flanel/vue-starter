<template>
    <form @submit.prevent="">
        <input type="email" v-model="email">
        <button @click="enter()"> {{buttonLabel}} </button>
    </form>
</template>

<script>
    export default {
        props: ['buttonLabel','header'],

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