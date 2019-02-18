<template>
    <div >
        <div>
            <app-journey-form :startApp='startApp' @openApp='startApp=$event'></app-journey-form>
            <div v-if='startApp' class="app_container">
                <div class='attractions'>
                    <app-attraction-form></app-attraction-form>
                    <app-journey-days></app-journey-days>
                </div>
                <app-take-list></app-take-list>
            </div>
        </div>
    </div>
</template>

<script>
    import JourneyForm from './components/JourneyForm.vue';
    import AttractionForm from './components/AttractionForm.vue';
    import JourneyDays from './components/JourneyDays.vue';
    import TakeList from './components/TakeList.vue';
    
    export default {
        data() {
            return {
                startApp:false
            }
        },
        components: {
            'app-journey-form' : JourneyForm,
            'app-attraction-form' : AttractionForm,
            'app-journey-days' : JourneyDays,
            'app-take-list' : TakeList
        }
    }

</script>

<style>
    .app_container {
        display: flex;
        width:95%;
        margin:auto;
    }
    .attractions {
        width:75%;
    }

</style>
