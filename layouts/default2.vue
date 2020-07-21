<template>
<v-app>
  
      <v-system-bar color="#009688">
        <v-spacer></v-spacer>
        <v-icon>mdi-wifi-strength-4</v-icon>
        <v-icon>mdi-signal-cellular-outline</v-icon>
        <v-icon>mdi-battery</v-icon>
        <span>12:30</span>
      </v-system-bar>
<div>
  <v-app-bar
      color="grey darken-3"
      dense
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>ประวัติของเบนเท็น</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
            v-for="n in 5"
            :key="n"
            @click="() => {}"
          >
            <v-list-item-title>Option {{ n }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
  </div>

  <!-- Sizes your content based upon application components -->
  <v-main>

    <!-- Provides the application the proper gutter -->
    <v-content>
      <nuxt/>
    </v-content>
  </v-main>
  
 <v-footer
    dark
    padless
  >
    <v-card
      class="flex"
      flat
      tile
    >
    <center>
      <v-card-title class="teal">
        <v-icon size="20">mdi-facebook</v-icon> &nbsp; &nbsp;
        <v-icon size="20">mdi-twitter</v-icon> &nbsp; &nbsp;
        <v-icon size="20">mdi-linkedin</v-icon> &nbsp; &nbsp;
        <v-icon size="20">mdi-instagram</v-icon> &nbsp; &nbsp;

      <v-spacer></v-spacer>
        <v-icon size="20">phone_in_talk</v-icon><span style="font-size: 15px;">: 088-422-7680</span> &nbsp; &nbsp;

      </v-card-title>
    </center>

      <v-card-text  class="py-2 white--text text-center" >
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </v-card-text>
    </v-card>
  </v-footer>

</v-app>
   
</template>
<script>
export default {
  data:function(){
  return{
     icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-linkedin',
        'mdi-instagram',
      ],
  }
  }

}
</script>
<style>
.box6 {
  background: #90cad6; /* For browsers that do not support gradients */
  background: -webkit-linear-gradient(left top, #90cad6, #30f186); /* For Safari 5.1 to 6.0 */
  background: -o-linear-gradient(bottom right, #90cad6, #30f186); /* For Opera 11.1 to 12.0 */
  background: -moz-linear-gradient(bottom right, #90cad6, #30f186); /* For Firefox 3.6 to 15 */
  background: linear-gradient(to bottom right, #90cad6, #30f186); /* Standard syntax */
}
</style>

