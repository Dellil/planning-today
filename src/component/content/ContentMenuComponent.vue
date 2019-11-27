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
                <app-item-overlay :value="isOverlaied" @overlayClosed="changeOverlayState"></app-item-overlay>
            </div>
        </v-col>
    </v-row>
</template>

<script>
import ItemOverlay from '../fixed/ItemOverlay.vue';
export default {
    components: {
        'app-item-overlay': ItemOverlay
    },
    data() {
        return {
            isOverlaied: false
        }
    },
    methods: {
        createBtnClicked(){
            this.isOverlaied = true;
        },
        changeOverlayState(){
            this.isOverlaied = false;
        }
    },

}
</script>

<style>

</style>