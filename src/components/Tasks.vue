<template>
    <v-card style = "height: 100%; overflow:hidden">
        <v-toolbar color="blue" dark>
            <v-toolbar-tittle>Create a Task</v-toolbar-tittle>
            <v-spacer></v-spacer>
            <v-btn icon>
                <v-icon>mdi-magnify</v-icon>
            </v-btn>
        </v-toolbar>
        <v-list two-line>
            <template
                v-for="(task, key) in tasks"
            >
                <Task  v-bind:key="key" :task="task" :index="key" />
            </template>
            
        </v-list>
        <v-divider></v-divider>
        <v-card-actions>
            <v-layout>
                <v-flex>
                    <NewTask/>
                </v-flex>
            </v-layout>
        </v-card-actions>
    </v-card>
</template>


<script>
import Task from './Task'
import NewTask from './NewTask'
export default {
    name: "tasks",
    components: { Task, NewTask },
    data: () => ({
        tasks: [
            {
                id: 1,
                title: "task tittle",
                sub_tittle:"This task contains  8 notes",
                isComplete: true
            },
            {
                id: 1,
                title: "task tittle",
                sub_tittle:"This task contains  8 notes"
            },
            {
                id: 1,
                title: "task tittle",
                sub_tittle:"This task contains  8 notes"
            },
            {
                id: 1,
                title: "task tittle",
                sub_tittle:"This task contains  8 notes"
            },
            {
                id: 1,
                title: "task tittle",
                sub_tittle:"This task contains  8 notes"
            },
            {
                id: 1,
                title: "task tittle",
                sub_tittle:"This task contains  8 notes"
            },
            {
                id: 1,
                title: "task tittle",
                sub_tittle:"This task contains  8 notes"
            },
            
        ]
    })
};
</script>