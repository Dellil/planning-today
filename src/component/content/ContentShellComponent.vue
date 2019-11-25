<template>
    <v-row
    style="height : 90%;"
    >
        <v-col
        style="height : 100%;"
        >
            <v-sheet
            width="100%"
            height="100%"
            class="ml-4"
            >
                <template
                v-if="componentIdx == 0"
                >
                    <app-content-main></app-content-main>
                </template>
                <template
                v-else
                >
                    <app-content-set-date></app-content-set-date>
                </template>
            </v-sheet>
        </v-col>
    </v-row>
</template>

<script>
import eventBus from '../../utils/eventBus.js';

import ContentMainComponent from './ContentMainComponent.vue';
import ContentSetDateComponent from './ContentSetDateComponent.vue';

export default {
    components: {
        'app-content-main': ContentMainComponent,
        'app-content-set-date': ContentSetDateComponent
    },
    data() {
        return {
            componentIdx : 0
        }
    },
    methods: {
        changeContentIdx: function(idx){
            this.componentIdx = idx;
        }
    },
    mounted: function() {
        eventBus.$on("getContentIndex", this.changeContentIdx);
    }
}
</script>

<style>

</style>