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
                text
                >
                    <v-icon v-text="mdiCheck"></v-icon>
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
                    <v-icon v-text="mdiDelete"></v-icon>
                </v-btn>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { mdiCheck, mdiDelete } from '@mdi/js';

export default {
    data() {
        return {
            length: 0,
            mdiCheck: mdiCheck,
            mdiDelete: mdiDelete,
            // Mock Object
            items: [
                {
                    text: '새벽기상',
                    order:1,
                    idx: 1
                },
                {
                    text: '알고리즘 문제 풀기',
                    order:1,
                    idx: 2
                },
                {
                    text: '독서',
                    order:2,
                    idx: 3
                },
                {
                    text: '집안일',
                    order:3,
                    idx: 4
                },
                {
                    text: '롸?',
                    order:4,
                    idx: 5
                }
            ]
        }
    },
}
</script>

<style>

</style>