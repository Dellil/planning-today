<template>
    <v-content>
        <!-- <v-sheet 
        class="d-flex justify-center">
            <app-content-shell></app-content-shell>
        </v-sheet> -->
        <v-container>
            <app-content-menu></app-content-menu>
            <app-content-shell></app-content-shell>
        </v-container>
    </v-content>
</template>

<script>
import ContentMenuComponent from './ContentMenuComponent.vue';
import ContentShellComponent from './ContentShellComponent.vue';

export default {
    components: {
        'app-content-menu': ContentMenuComponent,
        'app-content-shell': ContentShellComponent
    }
}
</script>

<style>

</style>