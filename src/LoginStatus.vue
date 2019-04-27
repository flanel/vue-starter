<template>
    <div>
        <h2> Jesteś zalogowany jako {{username}} </h2>
        <button @click="$emit('logout')"> Wyloguj </button>

        <ol>
            <li v-for="meeting in meetings">{{ meeting}}
            </li>
        </ol>

        <button @click="addMeeting()"> Dodaj nowe spotkanie </button>
        <input type="text" v-model="meetingName">
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
                ],
                meetingName: ''
            };
        },
        methods: {
            addMeeting() {
                this.meetings.push(this.meetingName);
                this.meetingName = ''
            }
        }
    }
</script>