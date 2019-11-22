<template>
    <div id="app">
        <v-app>
            <app-header></app-header>
            <app-menu></app-menu>
            <app-content></app-content>
            <app-footer></app-footer>
        </v-app>
    </div>
</template>

<script>
import HeaderComponent from './component/HeaderComponent.vue';
import MenuComponent from './component/menu/MenuComponent.vue';
import ContentComponent from './component/content/ContentComponent.vue';
import FooterComponent from './component/FooterComponent.vue';

export default {
    components : {
        'app-header': HeaderComponent,
        'app-menu': MenuComponent,
        'app-content': ContentComponent,
        'app-footer': FooterComponent
    },
    // data() {
    //     return {
            
    //     }
    // },
    created() {
        this.$vuetify.theme.dark = true
    }
}
</script>

<style>

</style>