<template>
    <v-container>
        <v-row 
        align="center"
        v-for="(item, i) in items" 
        :key="i"
        >
        <!-- DATE -->
            <v-col 
            cols="1"
            style="font-size: 0.8rem;"
            >
            {{ item.toDate }}
            </v-col>
            <v-col 
            cols="1"
            style="font-size: 0.8rem;"
            >
            {{ item.endDate }}
            </v-col>
        <!-- TEXT -->
            <v-col 
            cols="7"
            >
            {{ item.text }}
            </v-col>
        <!-- ORDER -->
            <v-col
            cols="2"
            class="text-center"
            >
            {{ item.order }}
            </v-col>
        <!-- DELETE-->
            <v-col cols="1">
                <v-btn
                block
                text
                >
                    <v-icon>{{ mdiDelete }}</v-icon>
                </v-btn>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { mdiDelete } from '@mdi/js';
export default {
    data(){
        return {
            mdiDelete: mdiDelete,
            items: [
                {
                    toDate: '2019-11-26',
                    endDate: '2019-11-30',
                    text: '12시 취침',
                    order: 1,
                    idx: 1
                },
                {
                    toDate: '2019-12-11',
                    endDate: '2019-12-30',
                    text: '운동가기',
                    order: 1,
                    idx: 2
                },
                {
                    toDate: '2019-09-18',
                    endDate: '2019-11-21',
                    text: '디자인 패턴',
                    order: 1,
                    idx: 3
                },
                {
                    toDate: '2019-08-01',
                    endDate: '2019-10-29',
                    text: '백수짓',
                    order: 1,
                    idx: 4
                }
            ]
        }
    },
}
</script>

<style>
</style>