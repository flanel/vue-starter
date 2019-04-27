<template>
    <div>
        <h2> Jesteś zalogowany jako {{username}} </h2>
        <button @click="$emit('logout')"> Wyloguj </button>

        <ol>
            <li v-for="meeting in meetings">{{ meeting}}
            </li>
        </ol>

    </div>
</template>

<script>
    export default {
        props: ['username'],
        data() {
            return {
                meetings: [
                    'MWO',
                    'TO',
                    'INNE',
                ]
            };
        }

    }
</script>