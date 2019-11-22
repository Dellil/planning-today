<template>
    <v-navigation-drawer 
    app
    clipped
    :value="drawer"
    >
        <v-list>
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

        <v-sheet
        height="300"
        >
            <v-calendar
            now="now"
            type="month"
            >
            </v-calendar>
        </v-sheet>
    </v-navigation-drawer>
</template>

<script>
export default {
    mounted(){
        setInterval(() => {
            this.drawer = !this.drawer
        }, 2000)();
    },
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