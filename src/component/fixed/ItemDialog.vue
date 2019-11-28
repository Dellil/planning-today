<template>
    <v-dialog
    persistent
    max-width="800px"
    :value="value"
    >
        <v-card>
            <v-form>
                <v-card-title>Add Your Plan</v-card-title>
                <v-card-text>
                    <v-container>
                        <v-row>
                            <v-col>
                                <v-checkbox
                                :label="checkBoxText"
                                >
                                </v-checkbox>
                            </v-col>
                        </v-row>
                        <v-row>
                            <!-- START DATE -->
                            <v-col
                            cols="6"
                            >
                                <v-menu
                                v-model="startMenu"
                                max-width="400px"
                                ref="startMenu"
                                :close-on-content-click="false"
                                :return-value.sync="startDate"
                                transition="slide-x-transition"
                                offset-y
                                >
                                    <template v-slot:activator="{on}">
                                        <v-text-field
                                        readonly
                                        outlined
                                        label="Start Date"
                                        color="pink dark-1"
                                        v-model="startDate"
                                        v-on="on"
                                        >
                                        </v-text-field>
                                    </template>
                                    <v-date-picker
                                    width="100%"
                                    no-title
                                    scrollable
                                    v-model="startDate"
                                    >
                                        <v-spacer></v-spacer>
                                        <v-btn
                                        text
                                        color="error"
                                        @click="startMenu = false"
                                        >
                                        Cancel
                                        </v-btn>
                                        <v-btn
                                        text
                                        color="white"
                                        @click="$refs.startMenu.save(startDate)"
                                        >
                                        OK
                                        </v-btn>
                                    </v-date-picker>
                                </v-menu>
                            </v-col>

                            <!-- END DATE -->
                            <v-col
                            cols="6"
                            >
                                <v-menu
                                v-model="endMenu"
                                max-width="400px"
                                ref="endMenu"
                                :close-on-content-click="false"
                                :return-value.sync="endDate"
                                transition="slide-x-reverse-transition"
                                offset-y
                                >
                                    <template v-slot:activator="{on}">
                                        <v-text-field
                                        readonly
                                        outlined
                                        label="End Date"
                                        color="pink dark-1"
                                        v-model="endDate"
                                        v-on="on"
                                        >
                                        </v-text-field>
                                    </template>
                                    <v-date-picker
                                    width="100%"
                                    no-title
                                    scrollable
                                    v-model="endDate"
                                    >
                                        <v-spacer></v-spacer>
                                        <v-btn
                                        text
                                        color="error"
                                        @click="endMenu = false"
                                        >
                                        Cancel
                                        </v-btn>
                                        <v-btn
                                        text
                                        color="white"
                                        @click="$refs.endMenu.save(endDate)"
                                        >
                                        OK
                                        </v-btn>
                                    </v-date-picker>
                                </v-menu>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col>
                                <v-text-field
                                outlined
                                label="Content"
                                color="pink dark-1"
                                >
                                </v-text-field>
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card-text>
                <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn
                    outlined
                    color="error"
                    @click="closeBtnClicked"
                    >
                    CANCEL
                    </v-btn>
                    <v-btn
                    outlined
                    @click="closeBtnClicked"
                    >
                    ADD
                    </v-btn>
                </v-card-actions>
            </v-form>
        </v-card>
    </v-dialog>
</template>

<script>
import eventBus from '../../utils/eventBus.js';
export default {
    props: ['value'],
    data() {
        return {
            checkBoxText: 'Today',
            startMenu: false,
            startDate: '',
            endMenu: false,
            endDate: ''
        }
    },
    methods: {
        closeBtnClicked: function(){
            this.$emit("overlayClosed");
            eventBus.$emit("setSnackBar", {
                text: 'Add Item Successfully!'
            })
        }
    },
}
</script>

<style>

</style>