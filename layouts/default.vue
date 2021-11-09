<template>
  <v-app>
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
            v-for="(item, i) in items"
            :key="i"
            :to="item.to"
            router
            exact
          >
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-title v-text="item.title" />
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-right="clipped" fixed app>
      <!-- <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>

      <v-btn icon @click.stop="clipped = !clipped">
        <v-icon>mdi-application</v-icon>
      </v-btn>

      <v-btn icon @click.stop="fixed = !fixed">
        <v-icon>mdi-minus</v-icon>
      </v-btn> -->

      <v-toolbar-title><Logo /></v-toolbar-title>

      <v-spacer />
      <!-- <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn> -->
      <!-- 
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn> -->

      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <Nuxt />

        <v-footer dark padless :absolute="true">
          <v-card class="flex" flat tile>
            <!-- <v-card-title style="background-color: #474747">
              <strong class="subheading"
                >Get connected with us on social networks!</strong
              >

              <v-spacer></v-spacer>

              <v-btn v-for="icon in icons" :key="icon" class="mx-4" dark icon>
                <v-icon size="24px">
                  {{ icon }}
                </v-icon>
              </v-btn>
            </v-card-title> -->

            <v-card-text class="py-2 white--text text-center">
              {{ new Date().getFullYear() }} —
              <strong>Axie Definity Academy</strong>
            </v-card-text>
          </v-card>
        </v-footer>
      </v-container>
    </v-main>
    <!-- <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light> mdi-repeat </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->
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
      items: [
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
