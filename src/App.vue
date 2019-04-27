<template>
  <div>
    <h1>Twój mail to  {{email}} </h1>
    <div v-if="email.length > 0">
        <h2>Witaj {{email}}</h2>
        <button @click="logOut"> Wyloguj </button>
    </div>

    <div v-else>
        <login-form @login="logIn($event)"></login-form>
    </div>
  </div>
</template>

<!--- ###################################################   -->

<script>
    import "milligram";
    import LoginForm from './LoginForm.vue';


    export default {
        components: {LoginForm},
        data() {
            return {
                email: 'mail@mail.pl'
            };
        },
        methods: {
            logIn(username) {
                this.email = username;
            },
            logOut() {
                this.email = '';
            }
        }
    }
</script>

<!--- ###################################################   -->

<style>

</style>
