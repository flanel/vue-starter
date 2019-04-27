<template>
  <div>
    <div v-if="email.length > 0">
        <login-status :username="email"
                      @logout="logMeOut()">
        </login-status>

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
    import LoginStatus from './LoginStatus.vue';

    export default {
        components: {LoginForm, LoginStatus},
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
