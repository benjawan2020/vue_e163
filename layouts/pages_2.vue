<template>
    <v-app>

        <v-system-bar dark color="primary">
      <v-spacer></v-spacer>
      <v-icon>mdi-wifi-strength-4</v-icon>
      <v-icon>mdi-signal-cellular-outline</v-icon>
      <v-icon>mdi-battery</v-icon>
      <span>12:37</span>
    </v-system-bar>

    <div>
        <v-app-bar
            color="#304FFE"
            dense
            dark
        >
    <nuxt-link to="/pages1"> 
      <v-icon>keyboard_backspace</v-icon></nuxt-link>&nbsp;&nbsp;&nbsp;&nbsp;

      <v-toolbar-title>Welcome</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>

    </v-app-bar>

    <v-tabs
    fixed-tabs
    background-color="#0099FF"
    dark
    color="#FFFFFF"
  >
    <v-tab>
      SING UP
    </v-tab>
    <v-spacer></v-spacer>
    <v-tab>
      SING IN
    </v-tab>
  </v-tabs>
    </div>


  <v-main>

    <!-- Provides the application the proper gutter -->
    <v-content>
      <nuxt/>
    </v-content>
  </v-main>
</v-app>
</template>