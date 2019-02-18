<template>
    <div>
        <h3>What attracion do you want to visit?</h3>
        <form>
            <label>Attraction name</label>
            <input type='text' v-model='attraction'>
            <button type='submit' @click.prevent='addAttraction'>Add</button>
        </form>
        <div v-if='attractions.length > 0'>
             <p>Lists of attractions which you want to visit</p>
            <ul >
                <li v-for='item in attractions'>{{item}}</li>
            </ul>
        </div>
    </div>
    
</template>

<script>
    export default {
        data() {
            return {
                attraction: '',
                attractions: [],
                isSubmitted: false
            }
        },
        methods: {
            addAttraction() {
                this.attractions.push(this.attraction);
            }
            
        }
    }

</script>

<style>

</style>