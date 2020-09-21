<template>
    <v-app class="bg1">
         <v-system-bar
          color="orange"
          :height="height"
          :lights-out="lightsOut"
          :window="window"
        >
          <v-icon>mdi-gmail</v-icon>
          <span>10 unread emails</span>
          <v-spacer></v-spacer>
          <v-icon>mdi-wifi-strength-4</v-icon>
          <v-icon>mdi-signal-cellular-outline</v-icon>
          <v-icon>mdi-battery</v-icon>
          <span>13:30</span>
        </v-system-bar>

      <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <lang-selector />

       <template v-slot:prepend>
        <v-list-item two-line>
          <v-list-item-avatar>
            <img src="images/ben.jpg" >
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>เบญจวรรณ สิงหอำพล</v-list-item-title>
            <v-list-item-subtitle>เข้าสู่ระบบแล้ว</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          @click=""
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

    </v-navigation-drawer>

    <div>
      <v-app-bar
      style="background: linear-gradient(to bottom left, #49c1b7 0%, #59c16c 80%);"
      dense
      dark
      >
  
    <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Page title</v-toolbar-title>

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

  <v-footer app>
    <!-- -->
  </v-footer>
</v-app>
</template>
<script>
import LangSelector from '~/components/lang-selector.vue'

export default {
  components: {
    LangSelector,
  },

  data () {
      return {
        items: [
          { title: 'Home', icon: 'mdi-home-city',link: 'index'},
          { title: 'ประวัติ', icon: 'mdi-account',link: 'home1' },
          { title: 'สมาชิก', icon: 'face' },
          { title: 'สินค้าแนะนำ', icon: 'touch_app' },
          { title: 'Users', icon: 'mdi-account-group-outline' },
          { title: 'Users', icon: 'mdi-account-group-outline' },
          { title: 'Users', icon: 'mdi-account-group-outline' },
        ],
      }
    },

  computed: {
    drawer: {
      get() {
        return this.$store.state.drawer
      },
      set(v) {
        this.$store.commit('setDrawer', v)
      },
    },
  }, // computed

  watch: {
    '$store.state.lang'() {
      this.$i18n.locale = this.$store.state.lang
    },
  }, // watch
}
</script>
</script>
<style scoped>
  .bg1 {
    background: linear-gradient(to bottom left, #59c16c 0%, #49c1b7 90%);
    padding-bottom: auto;
    padding-top: auto;
  }
  
</style>