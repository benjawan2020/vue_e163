<template>
<v-app>
  <v-card
    height="568"
  >
    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>

      <v-toolbar-title>Title</v-toolbar-title>
      <v-spacer></v-spacer>

    <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>
      
    
    <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-icon>mdi-dots-vertical</v-icon>
          
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-icon>
              <nuxt-link to="/">
              <v-icon>mdi-home</v-icon></nuxt-link>
            </v-list-item-icon>
            <v-list-item-title>index</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <nuxt-link to="/login">
              <v-icon>mdi-account</v-icon></nuxt-link>
            </v-list-item-icon>
            <v-list-item-title>Login</v-list-item-title>
          </v-list-item>

        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

 <!-- ส่วนบนสุดของเนื้อหา-->
        <v-content>
            <nuxt/>
        </v-content>

  </v-card>

  <v-footer app>
    By: Benjawan Singhaampol <v-spacer></v-spacer> <v-icon>perm_phone_msg</v-icon>:088-422-7680
    <!-- -->
  </v-footer>
  
</v-app>
</template>
<script>
  export default {
    data: () => ({
      drawer: false,
    }),
  }
</script>