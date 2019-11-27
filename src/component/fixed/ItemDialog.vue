<template>
    <v-dialog
    persistent
    max-width="800px"
    :value="value"
    >
        <v-card>
            <v-card-title>Add Your Plan</v-card-title>
            <v-card-text>
                <v-container>
                    <v-row>
                        <v-col>대충 체크박스라는 뜻</v-col>
                    </v-row>
                    <v-row>
                        <v-col>START DATE</v-col>
                        <v-spacer></v-spacer>
                        <v-col>END DATE</v-col>
                    </v-row>
                    <v-row>
                        <v-col>
                            여기다가 뭐할거임 꺄악
                        </v-col>
                    </v-row>
                </v-container>
                아아 여기는..
            </v-card-text>
            <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                outlined
                @click="closeBtnClicked"
                >
                ADD
                </v-btn>
                <v-btn
                outlined
                color="error"
                @click="closeBtnClicked"
                >
                CANCEL
                </v-btn>
                <v-spacer></v-spacer>
            </v-card-actions>
        </v-card>

    </v-dialog>
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