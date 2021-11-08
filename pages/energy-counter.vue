<template>
  <v-container>
    <v-row justify="space-around"> </v-row>

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
        <v-card width="400">
          <v-card-text>
            <div class="font-weight-bold ml-8 mb-2">History</div>

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
  font-size: 2.2em;
  font-weight: 500;
  color: #ffbf6b;
  padding-top: 30px;
}
.energy-counter-count {
  font-size: 128px;
  font-weight: 500;
}
</style>


