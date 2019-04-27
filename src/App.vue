<template>
  <div>
    <h1>Twój mail to  {{email}} </h1>
    <div v-if="email.length > 0">
        <h2>Witaj {{email}}</h2>
        <button @click="logMeOut"> Wyloguj </button>
    </div>

    <div v-else>
        <login-form @login="logMeIn($event)"
                    button-label="Zaloguj"
                    haeder="Logowanie">
        </login-form>
        <login-form @login="logMeIn($event)"
                    button-label="Zarejestruj"
                    haeder="Rejestracja">
        </login-form>

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
                email: ''
            };
        },
        methods: {
            logMeIn(username) {
                this.email = username;
            },
            logMeOut() {
                this.email = '';
            }
        }
    }
</script>

<!--- ###################################################   -->

<style>

</style>
