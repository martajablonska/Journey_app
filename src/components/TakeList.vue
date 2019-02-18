<template>
    <div class="things_container">
        <form v-if='!isSubmitted' class='things_form'>
            <label>What you need to take?</label>
            <div class="add">
                <input type='text' v-model='thing'>
                <button type='submit' @click.prevent='added'>Add</button>
            </div>
        </form>
        <div v-if='things.length > 0' class="things_list">
            <p>Things to take</p>
            <ul>
                <li v-for='thing in things'>{{thing}}</li>
            </ul>
        </div>
    </div>

</template>

<script>
    export default {
        data() {
            return {
                thing: '',
                things: []
            }
        },
        methods: {
            added() {
                this.things.push(this.thing);
            }
        }
    }
</script>

<style>
    .things_container {
        width:25%;
        height: 100vh;
        position: fixed;
        top:0;
        right:0;
        border: 1px solid black;
    }
    .things_form {
        display: flex;
        flex-direction: column;
        margin:10px;
    }
    
    .add {
        display: flex;
    }
    .things_list {
        margin: 10px;
    }
    ul {
        list-style-type: none;
    }
 
</style>