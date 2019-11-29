<template>
    <v-container>
        <v-card
        class="my-3 py-1"
        v-for="(item, i) in items" 
        :key="i"
        >
            <v-row 
            align="center"
            >
                <v-col
                cols="1"
                >
                    <v-btn
                    block
                    :text="item.textState"
                    :color="item.color"
                    @click="checkBtnClicked(item)"
                    class="ml-2"
                    >
                        <v-icon
                        v-text="item.icon" 
                        :color="item.iconColor"
                        >
                        </v-icon>
                    </v-btn>
                </v-col>
                <v-col 
                cols="10"
                >
                {{ item.text }}
                </v-col>
                <v-col cols="1">
                    <v-btn
                    block
                    text
                    class="ml-n2"
                    @click="deleteBtnClicked(item.idx)"
                    >
                        <v-icon>
                        {{mdiDelete}}
                        </v-icon>
                    </v-btn>
                </v-col>
            </v-row>
        </v-card>
    </v-container>
</template>

<script>
import { mdiCheck, mdiCheckOutline, mdiDelete } from '@mdi/js';
import eventBus from '../../utils/eventBus.js';

export default {
    data() {
        return {
            mdiCheck: mdiCheck,
            mdiCheckOutline: mdiCheckOutline,
            mdiDelete: mdiDelete,
            // Mock Object
            items: [
                {
                    isChecked: false,
                    textState: true,
                    color: 'white',
                    icon: mdiCheck,
                    iconColor: "white",
                    text: '새벽기상',
                    idx: 1
                },
                {
                    isChecked: false,
                    textState: true,
                    color: 'white',
                    icon: mdiCheck,
                    iconColor: "white",
                    text: '알고리즘 문제 풀기',
                    idx: 2
                },
                {
                    isChecked: false,
                    textState: true,
                    color: 'white',
                    icon: mdiCheck,
                    iconColor: "white",
                    text: '독서',
                    idx: 3
                },
                {
                    isChecked: false,
                    textState: true,
                    color: 'white',
                    icon: mdiCheck,
                    iconColor: "white",
                    text: '집안일',
                    idx: 4
                },
                {
                    isChecked: false,
                    textState: true,
                    color: 'white',
                    icon: mdiCheck,
                    iconColor: "white",
                    text: '롸?',
                    idx: 5
                }
            ]
        }
    },
    methods: {
        checkBtnClicked: function(item){
            if(!item.isChecked){
                item.color = 'grey darken-1';
            }else{
                item.color = 'white';
            }
            item.isChecked = !item.isChecked;
            item.textState = !item.textState;
        },
        deleteBtnClicked: function(idx){
            eventBus.$emit("setSnackBar", { text: 'Check List Item Removed Successfully!', component: 'main', idx: idx });
        }
    },
}
</script>

<style>

</style>