<template>
    <div class="days_container">
        <p>{{days}}</p>
        <div v-for='n in 10' class='day'>
            <p>A</p>
        </div>
    </div>
</template>

<script>
    import {daysBus} from '../main.js';
    
    export default {
        data() {
            return {
                days:null
            }
        },
        created() {
            daysBus.$on('numberOfDays', (data) =>
                        {this.days = data}
                       )
        }
        
    }
   
</script>

<style>
    .days_container {
        display: flex;
        flex-wrap:wrap;
        width:100%;
        margin:auto;
        justify-content: space-around;
    }
    .day {
        height: 250px;
        width: 250px;
        margin:20px;
        border: 1px solid black;
    }
</style>