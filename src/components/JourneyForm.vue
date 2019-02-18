<template>
    <div>
        <form v-if='!isSubmitted' class="title_form">
            <h3>Please write few basic informations about your journey</h3>
            <label>Your journey name</label>
            <input type='text' v-model='name'>
            <label>Where do you want to go?</label>
            <input type='text' v-model='place'>
            <label>How many days?</label>
            <input type='number' v-model='days'>
            <button type='submit' @click.prevent='submitted' class="title_btn">Submit</button>
        </form>
        <div v-if='isSubmitted' class="title_description">
            <h2>{{name}}</h2>
            <p>Destination: {{place}}</p>
        </div>
    </div>

</template>

<script>
    import {daysBus} from '../main.js';
    
    export default {
        data() {
            return {
                name: '',
                place: '',
                days: null,
                isSubmitted : false
            }
        },
        methods: {
            submitted() {
                this.isSubmitted = true;
                this.startApp = true;
                this.$emit('openApp', this.startApp);
                daysBus.$emit('numberOfDays', this.days);
            }
        }
    }
</script>

<style>
    .title_form {
        width:40vw;
        display: flex;
        flex-direction: column;
        margin:auto;
        margin-top:40px;
        justify-content: center;
    }
    label {
        margin: 10px 0;
    }
    input {
        height: 20px;
    }
    .title_btn {
        margin:20px 0;
        height: 30px;
    }
    .title_description {
        display: flex;
        flex-direction: column;
        justify-content: center;
        margin:auto;
        margin-top: 20px;
    }
</style>