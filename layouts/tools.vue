<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      right
      app
    >
      <v-list nav>
        <v-list-item-group>
          <v-list-item
            v-for="(item, i) in mainMenu"
            :key="i"
            :to="item.to"
            router
            exact>
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-title v-text="item.title" />
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-right="clipped" fixed app>
      <v-toolbar-title><Logo /></v-toolbar-title>

      <v-spacer />

      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
    </v-app-bar>
    <v-main>
      <!-- <v-container fluid style="position: absolute; width: 100%; height: 100%;" class="overflow-auto"> -->
        <v-container fluid class="overflow-auto">
        <Nuxt />

      </v-container>
      <v-footer dark padless :absolute="true">
          <v-card class="flex" flat tile>

            <v-card-text class="py-2 white--text text-center">
              {{ new Date().getFullYear() }} —
              <strong>Axie Definity Academy</strong>
            </v-card-text>
          </v-card>
        </v-footer>
    </v-main>
   
   
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      
      icons: ['mdi-facebook', 'mdi-twitter', 'mdi-discord'],
      title: 'Academy',
      miniVariant: false,
      right: false,
      rightDrawer: false,
      clipped: true,
      drawer: false,
      fixed: false,
      mainMenu: [
        {
          icon: 'mdi-apps',
          title: 'Start',
          to: '/',
        },
        {
          icon: 'mdi-newspaper-variant-multiple',
          title: 'News',
          to: '/posts',
        },
        {
          icon: 'mdi-newspaper-variant-multiple',
          title: 'Scholarship Info',
          to: '/scholarship',
        },
        {
          icon: 'mdi-lightning-bolt-outline',
          title: 'Cards Info',
          to: '/cards',
        },
        {
          icon: 'mdi-lightning-bolt-outline',
          title: 'Energy Counter',
          to: '/energy-counter',
        },
        {
          icon: 'mdi-star-box-multiple',
          title: 'Damage Calculator',
          to: '/damage-calculator',
        },
        {
          icon: 'mdi-help-circle',
          title: 'About us...',
          to: '/about',
        },
      ],
    }
  },
}
</script>

<style>

/* html {
  overflow-y: auto;
} */
</style>