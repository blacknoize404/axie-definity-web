<template>
  <v-container>
    <v-row justify="space-around">
      <v-card width="400">
        <v-img
          height="200px"
          src="https://cdn.pixabay.com/photo/2020/07/12/07/47/bee-5396362_1280.jpg"
        >
          <v-app-bar flat color="rgba(0, 0, 0, 0)">
            <v-app-bar-nav-icon color="white"></v-app-bar-nav-icon>

            <v-toolbar-title class="text-h6 white--text pl-0">
              Messages
            </v-toolbar-title>

            <v-spacer></v-spacer>

            <v-btn color="white" icon>
              <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
          </v-app-bar>

          <v-card-title class="white--text mt-8">
            <v-avatar size="56">
              <img
                alt="user"
                src="https://cdn.pixabay.com/photo/2020/06/24/19/12/cabbage-5337431_1280.jpg"
              />
            </v-avatar>
            <p class="ml-3">John Doe</p>
          </v-card-title>
        </v-img>

        <v-card-text>
          <div class="font-weight-bold ml-8 mb-2">Today</div>

          <v-timeline align-top dense>
            <v-timeline-item
              v-for="message in messages"
              :key="message.time"
              :color="message.color"
              small
            >
              <div>
                <div class="font-weight-normal">
                  <strong>{{ message.from }}</strong> @{{ message.time }}
                </div>
                <div>{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>
    </v-row>

    <div>
      <div class="energy-counter-title">Energy Counter</div>

      <v-col cols="auto" sm="auto" md="auto" align="center" justify="center">
        <!-- Using the elevation prop -->
        <div class="energy-counter-count">3</div>
        <div>
          <v-btn color="primary" nuxt class=""> - </v-btn>
          <v-btn color="primary" nuxt class="px-6"> Next Round </v-btn>
          <v-btn color="primary" nuxt class=""> + </v-btn>
        </div>
        <div>
          <v-btn color="primary" nuxt class="px-16 white my-2" outlined dark>
            New Game
          </v-btn>
        </div>
        <v-card class="mx-auto pa-4" style="max-width: 300px"> </v-card>

        <div class="my-6"></div>
      </v-col>
    </div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      messages: [
      {
        from: 'You',
        message: `-1 energy`,
        time: '10:43am',
        color: 'deep-purple lighten-1',
      },
      {
        from: 'You',
        message: `-1 energy`,
        time: '10:42am',
        color: 'deep-purple lighten-1',
      },
      {
        from: 'You',
        message: `+1 energy`,
        time: '10:37am',
        color: 'green',
      },
      {
        from: 'You',
        message: `-1 energy`,
        time: '9:47am',
        color: 'deep-purple lighten-1',
      },
    ],
    }
  },
}
</script>

<style scoped>
.energy-counter-title {
  font-size: 3em;
  font-weight: 500;
  color: #ffbf6b;
}
.energy-counter-count {
  font-size: 128px;
  font-weight: 500;
}
</style>


