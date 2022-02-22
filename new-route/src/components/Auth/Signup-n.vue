<template>
   <v-container fill-height>
       <v-layout align-center justify-center>
           <v-flex xs12 sm8 md4>
               <v-card class="elevation-12">
                   <v-toolbar dark color="blue">
                       <v-toolbar-title>Signup Form</v-toolbar-title>
                   </v-toolbar>
                   <v-card-text>
                       <v-form>
                           <v-alert :value="true" dark color="error">
                               <v-icon middle>mdi-alert</v-icon>
                               This user already exist, try a different set of data.
                           </v-alert>
                           <v-text-field 
                                prepend-icon="mdi-account" 
                                name="login" label="Username" 
                                :rules="[rules.required]"
                           >
                           </v-text-field>

                           <v-text-field
                                prepend-icon="mdi-email"
                                name="email"
                                label="Email"
                                :rules="[rules.required, rules.email]"
                           >
                           </v-text-field>

                           <v-text-field
                                prepend-icon="mdi-lock"
                                name="password"
                                label="Password"
                                :rules="passval"
                                type="password"
                                v-model="password"
                           >
                           </v-text-field>

                            <v-text-field
                                prepend-icon="mdi-lock"
                                name="password"
                                label="Confirm Password"
                                type="password"
                                v-model="confirm_password"
                                :rules="[rules.confirm]"
                                :error=!valid()
                           >
                           </v-text-field> <!--rules.required koy eğer does not match yazdıramazsan-->
                       </v-form>
                   </v-card-text>
                   <v-divider light></v-divider>
                        <v-card-actions>
                            <v-btn dark round color="black">Sign in</v-btn>
                            <v-spacer></v-spacer>
                            <v-btn round color="success">Register
                                <v-icon>mdi-chevron-up</v-icon>
                            </v-btn>
                        </v-card-actions>
               </v-card>
           </v-flex>
       </v-layout>
   </v-container>
</template>

<script>
export default {
    name:"Signup-n",
    data: () => ({
        password: '',
        confirm_password: '',
        rules: {
            required: value => !!value || "Required",
            email: value=> {
                const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
                return pattern.test(value) || "Invalid e-mail.";
            },
            confirm: value => {
                const degil = this.confirm_password === !this.password;
                return degil.test(value) || "Does not match";
            }
            },

        
        passval: [ 
            v => !!v || "Required",
            v => (v && v.length >= 5) || 'Password must have 5+ characters',
            v => /(?=.*[A-Z])/.test(v) || 'Must have one uppercase character', 
            v => /(?=.*\d)/.test(v) || 'Must have one number', 
            v => /([!@$%])/.test(v) || 'Must have one special character [!@#$%]' 

            ],

        }),
    methods: {
        valid(){
            return this.password ===this.confirm_password;
        }

    }
};
</script>