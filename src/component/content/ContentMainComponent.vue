<template>
    <v-container>
        <v-row 
        align="center"
        v-for="(item, i) in items" 
        :key="i"
        >
            <v-col 
            cols="1"
            >
                <v-btn
                block
                :text="item.textState"
                :color="item.color"

                @click="btnClicked(item)"
                >
                    <v-icon 
                    v-text="item.icon" 
                    :color="item.iconColor"
                    >
                    </v-icon>
                </v-btn>
            </v-col>
            <v-col 
            cols="8"
            >
            {{ item.text }}
            </v-col>
            <v-col
            cols="2"
            class="text-center"
            >
            {{ item.order }}
            </v-col>
            <v-col cols="1">
                <v-btn
                block
                text
                >
                    <v-icon 
                    v-text="mdiDelete"
                    >
                    </v-icon>
                </v-btn>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { mdiCheck, mdiCheckOutline, mdiDelete } from '@mdi/js';
import { isBuffer } from 'util';

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
                    order:1,
                    idx: 1
                },
                {
                    isChecked: false,
                    textState: true,
                    color: 'white',
                    icon: mdiCheck,
                    iconColor: "white",
                    text: '알고리즘 문제 풀기',
                    order:1,
                    idx: 2
                },
                {
                    isChecked: false,
                    textState: true,
                    color: 'white',
                    icon: mdiCheck,
                    iconColor: "white",
                    text: '독서',
                    order:2,
                    idx: 3
                },
                {
                    isChecked: false,
                    textState: true,
                    color: 'white',
                    icon: mdiCheck,
                    iconColor: "white",
                    text: '집안일',
                    order:3,
                    idx: 4
                },
                {
                    isChecked: false,
                    textState: true,
                    color: 'white',
                    icon: mdiCheck,
                    iconColor: "white",
                    text: '롸?',
                    order:4,
                    idx: 5
                }
            ]
        }
    },
    methods: {
        btnClicked: function(item){
            if(!item.isChecked){    
                item.color = 'grey darken-1';
            }else{
                item.color = 'white';
            }
            item.isChecked = !item.isChecked;
            item.textState = !item.textState;
        }
    },
}
</script>

<style>

</style>