<template>
  <div id="app">
    <v-app id="inspire">
      <v-app-bar
        absolute
        dark
        flat
        inverted-scroll
        scroll-target="#firstSection"
        elevation="0"
        class="homepage-toolbar"
      >
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
        <v-toolbar-title>Axie Definity Academy</v-toolbar-title>

        <v-spacer />
        <v-app-bar-items flex class="hidden-sm-and-down">
          <v-btn
            v-for="(item, i) in mainMenu"
            :key="i"
            :to="item.to"
            color="white"
            router
            flat
            text
            exact
            class="mx-1"
            >{{ item.title }}</v-btn
          >
        </v-app-bar-items>
      </v-app-bar>

      <section id='firstSection'>
        <v-layout row wrap>
          <v-flex xs12 sm12>
            <v-parallax height="750" dark src="rocke4.png">
              <v-layout column align-center justify-center>
                <v-layout
                  white--text
                  align-center
                  column
                  justify-center
                  style="margin-top: 25vh"
                >
                  <img
                    src="https://townshipcanada.com/static/logo.svg"
                    height="150"
                  />
                  <h3 class="display-3 ma-2 text-xs-center">Vuetify.js</h3>
                  <h4 class="subheading">Build your application today!</h4>
                  <v-flex wrap align-end justify-end text-xs-center>
                    <v-btn
                      dark
                      large
                      align-end
                      justify-end
                      color="blue lighten-2"
                      class="mt-4 elevation-0"
                      @click="
                        $vuetify.goTo('#ScholarshipProgram', 'easeInOutCubic')
                      "
                      >login</v-btn
                    >
                  </v-flex>
                </v-layout>
              </v-layout>
            </v-parallax>
          </v-flex>
        </v-layout>
      </section>

      <section id="ScholarshipProgram" style="margin: 200vh">
        <h1>Scholarship Program</h1>
        <h4>
          Y.A. Academy is an Axie Infinity scholarship program with the most
          clear scholar application process around. We are a family and strive
          to be the best Axie trainers we can be. Here are a few ways Y.A.A. is
          different from your normal scholarship program:
        </h4>
      </section>
    </v-app>
  </div>
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
          title: 'Scholarship',
          to: '/scholarship',
        },
        {
          title: 'Tools',
        },
        {
          icon: 'mdi-help-circle',
          title: 'About us...',
          to: '/about',
        },
      ],
    }
  },
  /* This solution is not definitive, it is only until vuetify implements a v-parallax with 100vh */
  //   mounted() {
  //     document.getElementById('parallax-hero').style.height = '100vh'
  //   },
}
</script>

<style>
.homepage-toolbar {
  background: rgba(222, 222, 222, 0.4) !important;
  background: transparent !important;
  -webkit-box-shadow: none !important;
  box-shadow: none !important;
}
.parallax {
  background-attachment: fixed;
  background-size: 100% auto;
}
</style>
