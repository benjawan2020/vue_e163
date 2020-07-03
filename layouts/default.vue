<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <lang-selector />
    </v-navigation-drawer>

    <v-app-bar
      app
      clipped-left
      dense
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title class="mr-12 align-center">
        <span class="title">CCOLLEGE</span>
      </v-toolbar-title>
    </v-app-bar>

    <v-content>
      <nuxt />
    </v-content>
  </v-app>
</template>

<script>
import LangSelector from '~/components/lang-selector.vue'

export default {
  components: {
    LangSelector,
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
