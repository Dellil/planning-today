<template>
    <v-list class="mt-4">
        <v-list-item-group mandatory>
            <v-list-item
            v-for="(item, i) in items"
            :key = "i"
            >
                <v-list-item-content>
                    <v-list-item-title v-text="item.title"></v-list-item-title>
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
                    title : "TODAY CHECK-LIST",
                    icon : ""
                },
                {
                    title : "SET THE DATE RANGE",
                    icon : ""
                }
            ]
        }
    }
}
</script>

<style>

</style>