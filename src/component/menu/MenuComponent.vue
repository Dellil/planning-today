<template>
    <v-navigation-drawer 
    app
    clipped
    >
        <div class="d-flex flex-column justify-space-between" id="menu-container">
            <app-list></app-list>
            <app-calendar></app-calendar>
        </div>     
    </v-navigation-drawer>
</template>

<script>
import CalendarComponent from './CalendarComponent.vue';
import ListComponent from './ListComponent.vue';


export default {
    components: {
        'app-calendar': CalendarComponent,
        'app-list': ListComponent
    },
    mounted(){
        // setInterval(() => {
        //     this.drawer = !this.drawer
        // }, 2000)();
    }

}
</script>

<style>
    #menu-container {
        height: 100%;
        overflow: hidden;
    }
</style>