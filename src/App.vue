<template>
  <div>
    <h1>Twój mail to  {{email}} </h1>
    <div v-if="loged==false">
      <div v-if="email.length < 10">Ale masz krótki adres!</div>
      <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
      <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
      <input type="email" v-model="email" >
      <button @click="alertMyEmail()"> Zaloguj </button>
    </div>
    <div v-else-if="loged==true">
      <h2>Witaj {{email}}</h2>
      <button @click="logOut"> Wyloguj </button>
    </div>
  </div>
</template>

<script>

export default {
    data() {
        return {
            email: 'mail@mail.pl',
            password: '',
            loged: false
        };
    },
    methods: {
        alertMyEmail() {
            alert("zalogowano");
            this.loged = true;
        },
        logOut() {
            alert("wylogowano");
            this.loged = false;
        }
    }
}

</script>

<style>

</style>
