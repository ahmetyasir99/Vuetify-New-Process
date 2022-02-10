<template>
    <v-navigation-drawer permanent style="width: 100%">
        <v-toolbar color="blue" dark>
            <v-toolbar-title>Your Lists</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn icon>
                <v-icon>mdi-magnify</v-icon>
            </v-btn>
        </v-toolbar>
        <v-list nav>
            <v-list-item>
                <v-list-item-content>
                    <v-list-item-title>Create a new list</v-list-item-title>
                </v-list-item-content>      
                <v-list-item-action>
                    <v-icon>mdi-plus</v-icon>
                </v-list-item-action>
            </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list>
            <v-list-item 
                v-for="(list,key) in lists"
                v-bind:key="key"
            >
                <v-list-item-content>
                    <v-list-item-title>{{ list.title }}</v-list-item-title>
                </v-list-item-content>
                <v-list-item-action>
                    <v-list-item-title>{{ list.tasks }}</v-list-item-title>
                </v-list-item-action>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>
</template>

<script>
export default {
    name:"lists",
    data: () =>({

        lists:[
            {
            id:1,
            title: "List",
            tasks: 12
            },
            {
            id: 1,
            title: "List",
            tasks: 45               
            },
            {
            id: 1,
            title: "List",
            tasks: 66               
            },
            {
            id: 1,
            title: "List",
            tasks: 3               
            },                         
        ]
    })
}
</script>