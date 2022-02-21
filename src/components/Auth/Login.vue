<template>
    <v-container fluid fill-height> <!--{ ortalamak için kullanıyoruz }-->
        <v-layout align-center justify-center>   <!--{ ortalamak için kullanıyoruz }-->
            <v-flex xs12 sm8 md4>  <!--{ v-flex is used for columns xs12(ekstra small) sm8(8 columns)   }-->
                <v-form>
                    <v-card class="elevation-12"> <!--{ elevation: gölgenin yumuşaklığını ayarlıyor }-->
                        <v-toolbar dark color="blue"> <!--{ dark yazı rengini açık yapıyor tema dark olduğunda kullanılıyor olmalı }-->
                            <v-toolbar-title>Login Form</v-toolbar-title>
                        </v-toolbar>
                        <v-card-text>
                           <v-text-field v-model ="username" prepend-icon="mdi-account" name ="login" label="Username" type="text"></v-text-field> 
                           <v-text-field v-model ="password" prepend-icon="mdi-lock" name ="password" label="Password" type="password"></v-text-field> 
                        </v-card-text>
                        <v-divider></v-divider>
                        <v-card-actions>
                            <v-btn dark color="indigo" round>Sign in</v-btn>
                            <v-btn dark color="primary" round v-model = "login" @click="submit">
                                Login 
                                <v-icon>mdi-chevron-right</v-icon>
                            </v-btn>
                            <v-spacer></v-spacer>
                            <div class="text-center">
                                <v-dialog
                                v-model="dialog"
                                persistent
                                max-width="400"
                                @keydown.esc = "dialog = false"
                                >
                                <template v-slot:activator="{ on, attrs }">
                                    <v-btn dark color="pink" round
                                    v-bind="attrs"
                                    v-on="on"
                                    >
                                    Sign in w/ <v-icon>mdi-twitter</v-icon><v-icon>mdi-facebook</v-icon><v-icon>mdi-instagram</v-icon> 
                                    </v-btn>
                                </template>
                                <v-card>
                                    <v-toolbar color="pink" dark dense class="text-h5"> <!--{ dark yazı rengini açık yapıyor tema dark olduğunda kullanılıyor olmalı }-->
                                        <v-toolbar-title> Sign in with your social media account</v-toolbar-title>
                                    </v-toolbar>
                                    <v-spacer></v-spacer>
                                    <v-card-actions>
                                    <v-spacer></v-spacer>
                                       
                                        <v-btn
                                            block outlined color="pink"
                                            @click="dialog = false"
                                            
                                        >
                                            <v-icon left>mdi-twitter</v-icon>Login with Twitter 
                                        </v-btn>
                                        <v-spacer></v-spacer>                         
                                    </v-card-actions>
                                    <v-card-actions>
                                    <v-btn
                                            block outlined color="pink"
                                            @click="dialog = false"
                                        >
                                            <v-icon left>mdi-facebook</v-icon>Login with Facebook 
                                    </v-btn>
                                    </v-card-actions>
                                    <v-card-actions>
                                    <v-btn
                                            block outlined color="pink"
                                            @click="dialog = false"
                                        >
                                            <v-icon left>mdi-instagram</v-icon>Login with Instagram 
                                        </v-btn>
                                    </v-card-actions>
                                </v-card>
                                </v-dialog>                            
                            </div>                    
                        </v-card-actions>
                    </v-card>
                </v-form>
            </v-flex>
        </v-layout>
    </v-container>
</template>



<script>
import axios from 'axios';
export default {
    name: "login"
    ,data () {
      return {
        username:'',
        password:'',
        dialog: false,
      }
    },
    methods: {
        submit(){
            console.log(this.username, this.password)
            
            axios.post("https://reqres.in/api/login", this.username,this.password)
            .then(response => this.articleId = response.data.id);
        }
    },

}

</script>