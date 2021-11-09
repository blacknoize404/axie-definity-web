<template lang="html">
  <div>
    <v-btn color="primary" class="px-6" @click="refresh"> Refresh </v-btn>
    <p v-if="$fetchState.pending">Loading....</p>
    <p v-else-if="$fetchState.error">Error while fetching data</p>
    <ul v-else>
      <v-card class="mx-auto text-center" color="green" dark max-width="600">
        <v-card-text>
          <v-sheet color="rgba(0, 0, 0, .12)">
            <v-sparkline
              :value="value"
              color="rgba(255, 255, 255, .7)"
              height="100"
              padding="24"
              stroke-linecap="round"
              smooth
            >
              <!-- <template #label="item"> ${{ item.value[0] }} </template> -->
            </v-sparkline>
          </v-sheet>
        </v-card-text>

        <v-card-text>
          <div class="text-h4 font-weight-thin">SLP Prices Last 24h</div>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions class="justify-center">
          <v-btn block text> Go to Report </v-btn>
        </v-card-actions>
      </v-card>
      <!-- <li v-for="(last_build, index) in updates" :key="index.id">
        {{ last_build }}
      </li>

      <li>
        SLP to USD Price -> {{ slp_price['smooth-love-potion'].usd }} USD
        <br>
        Market change -> {{ slp_price['smooth-love-potion'].usd_24h_change }}%
        <br>
        Market change -> {{ slp_price_full['prices'] }}
      </li> -->
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      axie_stats: [],
      slp_price: [],
      slp_price_full: [],
      value: [
        0.07627110083898975,
        0.07595199786574941,
        0.07495481427266242,
        0.07526989499960446,
        0.07526989499960446,
        0.07575960195993034,
        0.07669398027985345,
        0.07640198745642007,
        0.0758184438999842,
        0.07667914294276844,
        0.07678273871263624,
        0.07759091385857396,
        0.07643422529582182,
        0.07605033929677694,
        0.0756889970670796,
        0.07530201397115992,
        0.07457244313151597,
        0.074555850558216,
        0.074560511111403,
        0.07454411828319214,
        0.07478987930970006,
        0.0748947368280464,
        0.07446474725603533,
        0.07396020484320442,
        0.07271889191307161,
        0.07324400508731191,
      ]
    }
  },

  async fetch() {
    // this.updates = await fetch('https://game-api.axie.technology/stats', {
    //   method: 'GET',
    // }).then((res) => res.json())

    this.slp_price = await fetch(
      'https://api.coingecko.com/api/v3/simple/price?ids=smooth-love-potion&vs_currencies=usd&include_24hr_change=true',
      { method: 'GET' }
    ).then((res) => res.json())
    this.slp_price_full = await fetch(
      'https://api.coingecko.com/api/v3/coins/smooth-love-potion/market_chart?vs_currency=usd&days=1&interval=hourly',
      { method: 'GET' }
    ).then((res) => res.json())

    //   async fetch() {
    //     this.updates = await fetch(
    //       'https://json.psty.io/api_v1/stores/micuentanauta_version_manifest',
    //       {
    //         method: 'GET', // or 'PUT'
    //         headers: {
    //           'Api-Key': '7b10a2aa-3c55-43a4-a518-e1e948d81b7f',
    //         },
    //       }
    //     ).then((res) => res.json())
  },
  methods: {
    refresh() {
      this.$nuxt.refresh()
    },
  },
}
</script>
<style lang="css" scoped></style>
