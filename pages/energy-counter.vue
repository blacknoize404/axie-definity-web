<template >
  <v-container dark>
    <v-row justify="space-around"> </v-row>

    <div>
      <div class="energy-counter-title">Energy Counter</div>

      <v-col cols="auto" sm="auto" md="auto" align="center" justify="center">
        <!-- Using the elevation prop -->
        <div class="energy-counter-count">{{ energy }}</div>
        <div>
          <v-btn
            :disabled="remEnergyButtonDisable"
            color="primary"
            @click="remEnergy"
          >
            -
          </v-btn>
          <v-btn color="primary" class="px-6" @click="nextRound">
            Next Round
          </v-btn>
          <v-btn
            :disabled="addEnergyButtonDisable"
            color="primary"
            @click="addEnergy"
          >
            +
          </v-btn>
        </div>
        <div>
          <v-btn
            color="primary"
            nuxt
            class="px-16 white my-2"
            outlined
            @click="newGame"
          >
            New Game
          </v-btn>
        </div>
        <v-card width="400" class="mb-8">
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
                  <strong>{{ message.message }}</strong>
                </div>
              </v-timeline-item>
            </v-timeline>
          </v-card-text>
        </v-card>
        <div class="my-2"></div>
      </v-col>
    </div>
  </v-container>
</template>

<script>
export default {
  layout: 'tools',
  data() {
    return {
      energy: 3,
      round: 1,
      remEnergyButtonDisable: false,
      addEnergyButtonDisable: false,
      messages: [],
    }
  },
  mounted() {
    this.newGame()
  },
  methods: {
    formatAMPM(date) {
      let hours = date.getHours()
      let minutes = date.getMinutes()
      let seconds = date.getSeconds()
      const ampm = hours >= 12 ? 'pm' : 'am'
      hours = hours % 12
      hours = hours || 12 // the hour '0' should be '12'
      minutes = minutes < 10 ? '0' + minutes : minutes

      if (seconds < 10) {
        seconds = "0" + seconds
      }

      const strTime = hours + ':' + minutes + ':' + seconds + ' ' + ampm
      return strTime
    },
    resetLog() {
      this.messages = []
    },
    logEnergyActions(title, color) {
      const today = new Date()
      this.messages.unshift({
        from: title,
        time: this.formatAMPM(today),
        color: color + ' lighten-1',
      })
    },

    addEnergy() {
      if (this.energy < 10) {
        this.energy += 1
        this.logEnergyActions('+1 Energy', 'light-blue darken-3')

        this.remEnergyButtonDisable = false
      }

      if (this.energy === 10) {
        this.addEnergyButtonDisable = true
      }
    },
    remEnergy() {
      if (this.energy > 0) {
        this.energy -= 1
        this.logEnergyActions('-1 Energy', 'deep-orange')

        this.addEnergyButtonDisable = false
      }

      if (this.energy === 0) {
        this.remEnergyButtonDisable = true
      }
    },
    nextRound() {

      let addedEnergy = ' (+2)'
      if (this.energy < 9) {
        this.energy += 2
      } else if (this.energy === 9) {
        this.energy += 1
      }
      if (this.energy === 10) {
        this.addEnergyButtonDisable = true
        addedEnergy = ''
      }
      if (this.energy > 0) {
        this.remEnergyButtonDisable = false
      }
      this.round += 1
      this.logEnergyActions('Round ' + this.round + addedEnergy, 'teal darken-1')
    },
    newGame() {
      
      this.round = 1
      this.energy = 3
      this.resetLog()
      this.logEnergyActions('New Game Started', 'deep-purple')
      this.addEnergyButtonDisable = false
      this.remEnergyButtonDisable = false
    },
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


