<template>
   <v-card>
     <v-card-title>
       <h1>Login</h1>
     </v-card-title>
     <v-card-text>
       <v-form>
         <v-text-field  prepend-icon="mdi-account-circle" label="Username" />
         <v-text-field  prepend-icon="https" append-icon="visibility_off" label="Password" />
       </v-form>
     </v-card-text>
     <v-card-actions>
        <nuxt-link to="/Register">
            <v-btn color="success">REGISTER</v-btn> </nuxt-link>
             <v-spacer></v-spacer>
            <v-btn color="primary">LOGIN</v-btn>
     </v-card-actions>
   </v-card>
</template>
