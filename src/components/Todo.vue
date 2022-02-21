<template>
    <div style = "max-height: 96.3vh; height: 100%">
        <v-conatiner fluid fill-height pl-0>
            <v-layout row align-space-between justify-space-between>
                <v-flex lg3 pr-2>
                    <Lists/>
                </v-flex>
                <v-flex lg6 pr-2 pl-2>
                    <Tasks/>
                </v-flex>
                <v-flex lg3 pl-2>
                    Options
                </v-flex>
            </v-layout>
        </v-conatiner>
        <v-footer bottom fixed height = "auto" color = "indigo">
            <v-layout justify-center>
                <v-flex indigo white--text text-center>
                    &copy; 2022
                    <strong>Open Zeka</strong>
                </v-flex>
            </v-layout>
        </v-footer>
    </div>
</template>

<script>
import Lists from './Lists';
import Tasks from './Tasks';
export default {
    name: "todo",
    components: {Lists, Tasks}
}
</script>