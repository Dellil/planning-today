<template>
    <v-content>
        <v-sheet 

        class="d-flex justify-center">
            <app-content-shell></app-content-shell>
        </v-sheet>
    </v-content>
</template>

<script>
import ContentShellComponent from './ContentShellComponent.vue';
a = {
    
}
export default {
    components: {
        'app-content-shell': ContentShellComponent
    }
}
</script>

<style>

</style>