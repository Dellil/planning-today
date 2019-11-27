<template>
    <v-row>
        <v-col>
            <div>
                <v-btn
                large
                @click="createBtnClicked()"
                >
                Create
                </v-btn>
                <v-btn
                large
                class="ml-4"
                >
                Delete
                </v-btn>
            </div>
        </v-col>
    </v-row>
</template>

<script>
import eventBus from '../../utils/eventBus.js';

export default {
    data() {
        return {
            idx: 0
        }
    },
    mounted() {
        eventBus.$on("passIdxToCreateBtn", this.changeContentIdx);
    },
    methods: {
        changeContentIdx: function(idx){
            this.idx = idx;
        },
        createBtnClicked(idx){
            
        }
    },

}
</script>

<style>

</style>