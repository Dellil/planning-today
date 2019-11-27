<template>
    <v-overlay :value="value">
        <v-btn @click="closeBtnClicked">
        하와와와와
        </v-btn>
    </v-overlay>
</template>

<script>
export default {
    props: ['value'],
    data() {
        return {

        }
    },
    methods: {
        closeBtnClicked: function(){
            this.$emit("overlayClosed");
        }
    },
}
</script>

<style>

</style>