<template>
    <v-container>
        <v-card
        class="my-3"
        v-for="(item, i) in items" 
        :key="i"
        >
            <v-row 
            align="center"
            >
                <!-- DATE -->
                <v-col 
                cols="2"
                class="text-center"
                >
                {{ item.toDate }}
                </v-col>
                <v-col 
                cols="2"
                class="text-center"
                >
                {{ item.endDate }}
                </v-col>
                <!-- TEXT -->
                <v-col 
                cols="7"
                >
                {{ item.text }}
                </v-col>
                <!-- DELETE-->
                <v-col cols="1">
                    <v-btn
                    block
                    text
                    >
                        <v-icon>
                        {{ mdiDelete }}
                        </v-icon>
                    </v-btn>
                </v-col>
            </v-row>
        </v-card>
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
                    idx: 1
                },
                {
                    toDate: '2019-12-11',
                    endDate: '2019-12-30',
                    text: '운동가기',
                    idx: 2
                },
                {
                    toDate: '2019-09-18',
                    endDate: '2019-11-21',
                    text: '디자인 패턴',
                    idx: 3
                },
                {
                    toDate: '2019-08-01',
                    endDate: '2019-10-29',
                    text: '백수짓',
                    idx: 4
                }
            ]
        }
    },
}
</script>

<style>
</style>