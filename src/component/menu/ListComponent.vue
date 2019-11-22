<template>
    <v-list class="mt-4">
        <v-list-item-group mandatory>
            <v-list-item
            v-for="(item, i) in items"
            :key = "i"
            class="pa-3"
            >
                <v-list-item-content>
                    <v-list-item-title v-text="item.title"></v-list-item-title>
                    <v-list-item-subtitle v-text="item.subtitle"></v-list-item-subtitle>
                </v-list-item-content>
            </v-list-item>
        </v-list-item-group>
    </v-list>
</template>

<script>
export default {
    data() {
        return {
            drawer: true,
            items: [
                {
                    title : "CHECK-LIST",
                    subtitle: "PLAN YOUR TODAY",
                    icon : ""
                },
                {
                    title : "SET THE DATE RANGE",
                    subtitle: "정공용",
                    icon : ""
                }
            ]
        }
    }
}
</script>

<style>

</style>