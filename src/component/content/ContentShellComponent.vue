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

            >
                <template>
                    <component :is="componentInstance" />
                </template>
            </v-sheet>
        </v-col>
    </v-row>
</template>

<script>
import eventBus from '../../utils/eventBus.js';

export default {
    data() {
        return {
            componentIdx : 0
        }
    },
    mounted() {
        eventBus.$on("getContentIndex", this.changeContentIdx);
    },
    methods: {
        changeContentIdx: function(idx){
            this.componentIdx = idx;
            eventBus.$emit("passIdxToCreateBtn", this.componentIdx);
        }
    },
    computed: {
        componentInstance() {
            const name = this.componentIdx == 0 ? 'ContentMainComponent' : 'ContentSetDateComponent';
            return () => import(`./${name}.vue`);
        }
    },
}
</script>

<style>

</style>