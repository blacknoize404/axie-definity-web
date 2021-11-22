<template>
  <div id="app">
    <v-app id="inspire">
      <v-app-bar
        fixed
        dark
        :elevation="elevation"
        scroll-target="#scholarship"
        :class="[
          'homepage_toolbar',
          { homepage_toolbar_fill: scrollPosition >= 50 },
        ]"
      >
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
        <v-toolbar-title><Logo /></v-toolbar-title>

        <v-spacer />
        <v-app-bar-items flex class="hidden-sm-and-down">
          <v-btn
            v-for="(item, i) in mainMenu"
            :key="i"
            color="white"
            flat
            text
            class="mx-1"
            @click="$vuetify.goTo(item.to, 'easeInOutCubic')"
            >{{ item.title }}</v-btn
          >
        </v-app-bar-items>
      </v-app-bar>
      <v-main>
        <v-container fluid>
          <section id="start">
            <v-layout row wrap>
              <v-flex xs12 sm12>
                <v-parallax style="height: 100vh" dark src="rocke4.png">
                  <v-row align="center" justify="center">
                    <v-col class="text-center" cols="12">
                      <kinesis-container>
                        <kinesis-element :strength="20" type="depth">
                          <v-img src="logo.svg" height="150" contain />
                        </kinesis-element>
                        <kinesis-element :strength="20" type="depth">
                          <h3 class="display-3 ma-2 text-center">
                            Axie Definity
                          </h3>
                        </kinesis-element>
                      </kinesis-container>

                      <h4 class="subheading">The academy for all.</h4>
                      <v-flex wrap align-end justify-end text-xs-center>
                        <v-btn
                          dark
                          large
                          align-end
                          justify-end
                          color="blue lighten-2"
                          class="mt-4 elevation-0"
                          @click="
                            $vuetify.goTo('#scholarship', 'easeInOutCubic')
                          "
                          >-</v-btn
                        >
                      </v-flex>
                    </v-col>
                  </v-row>
                </v-parallax>
              </v-flex>
            </v-layout>
          </section>

          <section id="scholarship" class="py-16">
            <v-container>
              <v-lazy
                :options="{
                  threshold: 0.5,
                }"
                min-height="200"
                transition="fade-transition"
              >
                <div>
                  <span class="text-h3 text-h4-sm">Apply Scholarship</span>

                  <p
                    class="text-h5 text-h5-sm"
                    style="margin: 30px 0px 0px 0px"
                  >
                    <span style="color: orange">Axie Definity Academy</span> is
                    an Axie Infinity scholarship program with the most clear
                    scholar application process around. We are a family and
                    strive to be the best Axie trainers we can be. Here are a
                    few ways Y.A.A. is different from your normal scholarship
                    program:
                  </p>
                </div>
              </v-lazy>
              <v-row style="justify-content: center" justify="space-between">
                <v-col
                  v-for="(item, i) in scholarship"
                  :key="i"
                  cols="16"
                  sm="4"
                >
                  <v-card
                    class="pa-2"
                    tile
                    elevation="0"
                    style="text-align: center"
                  >
                    <v-card-title
                      class="text-h5"
                      style="justify-content: center; word-break: break-word"
                      >{{ item.title }}</v-card-title
                    >
                    {{ item.description }}
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </section>

          <v-lazy
            :options="{
              threshold: 0.5,
            }"
            min-height="200"
            transition="fade-transition"
          >
            <section id="leaderboards">
              <v-layout row wrap>
                <v-flex xs12 sm12>
                  <v-parallax style="height: 600px" dark src="01 min.jpg">
                    Leaderboards
                  </v-parallax>
                </v-flex>
              </v-layout>
            </section>
          </v-lazy>
          <section id="exams" class="py-16">
            <v-container class="py-16">
              <v-lazy
                :options="{
                  threshold: 0.5,
                }"
                min-height="200"
                transition="fade-transition"
              >
                <div>
                  <span class="text-h3 text-h4-sm">Apply Scholarship</span>

                  <p
                    class="text-h5 text-h5-sm"
                    style="margin: 30px 0px 0px 0px"
                  >
                    <span style="color: orange">Axie Definity Academy</span> is
                    an Axie Infinity scholarship program with the most clear
                    scholar application process around. We are a family and
                    strive to be the best Axie trainers we can be. Here are a
                    few ways Y.A.A. is different from your normal scholarship
                    program:
                  </p>
                </div>
              </v-lazy>
              <v-row style="justify-content: center" justify="space-between">
                <v-col
                  v-for="(item, i) in scholarship"
                  :key="i"
                  cols="16"
                  sm="4"
                >
                  <v-card
                    class="pa-2"
                    tile
                    elevation="0"
                    style="text-align: center"
                  >
                    <v-card-title
                      class="text-h5"
                      style="justify-content: center; word-break: break-word"
                      >{{ item.title }}</v-card-title
                    >
                    {{ item.description }}
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </section>

          <v-footer dark padless absolute>
            <v-card class="flex" flat tile>
              <v-card-text class="py-5 white--text text-center">
                {{ new Date().getFullYear() }} —
                <strong>Axie Definity Academy</strong>
              </v-card-text>
            </v-card>
          </v-footer>
        </v-container>
      </v-main>
    </v-app>
  </div>
</template>

<script>
export default {
  data() {
    return {
      scholarship: [
        {
          title: 'Value Based Scholarships',
          description:
            "All scholarships given at Yuuki's Axie Academy are value based. We have developed a system for scholars to work hard to get into the academy. This system is outlined in detail on our discord server here.",
        },
        {
          title: 'Axie Training Program',
          description:
            'We pride ourselves in constantly testing our Axie Infinity knowledge and growing together, just like at a real school. We offer exams, gameplay breakdown, training sessions, scholar vs scholar training sessions, and more to both scholars and potential scholars.',
        },
        {
          title: 'All Inclusive',
          description:
            'We not only focus on bringing in scholars to our academy, but also highly encourage our members to apply at other scholarships, share their knowledge on Axie, and grow with scholars from other guilds! There is so much opportunity in Axie Infinity, our ultimate purpose is to get you there!',
        },
      ],
      elevation: 0,
      scrollPosition: null,
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
          to: '#start',
        },
        {
          icon: 'mdi-newspaper-variant-multiple',
          title: 'Scholarship',
          to: '#scholarship',
        },
        {
          icon: 'mdi-newspaper-variant-multiple',
          title: 'Leaderboards',
          to: '#leaderboards',
        },
        {
          icon: 'mdi-newspaper-variant-multiple',
          title: 'News',
          to: '#news',
        },
        {
          title: 'Tools',
        },
        {
          icon: 'mdi-help-circle',
          title: 'About us...',
          to: '#about',
        },
      ],
    }
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll)
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY
      if (this.scrollPosition >= 50) {
        this.elevation = 10
      }
      else {
        this.elevation = 0
      }
    },
  },

  /* This solution is not definitive, it is only until vuetify implements a v-parallax with 100vh */
  //   mounted() {
  //     document.getElementById('parallax-hero').style.height = '100vh'
  //   },
}
</script>

<style>
.homepage_toolbar {
  background: transparent !important;
  -webkit-box-shadow: none !important;
  box-shadow: none !important;
}

.homepage_toolbar_fill {
  background: #363941 !important;
}
</style>
