<template>
  <v-container>
    <v-row justify="space-around"> </v-row>

    <div>
      <div class="energy-counter-title">Energy Counter</div>

      <v-col cols="auto" sm="auto" md="auto" align="center" justify="center">
        <v-card
          class="d-flex justify-center mb-6"
          :color="$vuetify.theme.dark ? 'grey darken-3' : 'grey lighten-4'"
          flat
          tile
        >
          <v-card v-for="n in 3" :key="n" class="pa-2" outlined tile>
            justify-center
          </v-card>
        </v-card>

        <v-card
          class="
            d-flex
            flex-wrap
            align-content-between
            justify-space-around
            mb-6
          "
          :color="$vuetify.theme.dark ? 'grey darken-3' : 'grey lighten-4'"
          flat
          tile
        >
          <v-card v-for="n in 9" :key="n" class="rounded-xl">
            <div class="card_item_skill_name">Swift Escape</div>
            <div
              style="
                width: 300px;
                background-image: url('cards/aquatic-back-06.png');
                background-position: center center;
                background-size: contain;
                padding-bottom: 133.333%;
              "
            />

            <div class="card_item_energy">1</div>
            <div class="card_item_effect">
              <img
                src="https://storage.googleapis.com/axie-cdn/game/cards/effect-icons/speed-up.png"
                class="card_item_effect_image"
              />
            </div>
            <div class="card_item_description">
              Aplica Velocidad+ a este Axie durante 2 asaltos cuando sea atacado
            </div>
            <div class="card_item_statistic card_item_statistic_attack">
              <div class="card_item_statistic_wrapper">
                <svg
                  viewBox="0 0 8 15"
                  fill="#BB374F"
                  class="card_item_statistic_icon"
                >
                  <g fill-rule="evenodd">
                    <path
                      d="M3.964.5l-2.49 1.786.971 7.922H5.483l.97-7.922zM3.964 12.694H2.72v2.26h2.49v-2.26zM3.964 10.718H.667v1.452H7.262v-1.452z"
                    ></path>
                  </g>
                </svg>
                <div class="card_item_statistic_value">105</div>
              </div>
            </div>
            <div class="card_item_statistic card_item_statistic_defense">
              <div class="card_item_statistic_wrapper">
                <svg
                  viewBox="936 3010 10 13"
                  fill="#319B6B"
                  class="card_item_statistic_icon"
                >
                  <path
                    d="M944.895 3018.624c-.748 1.524-1.928 2.716-3.668 3.82a.448.448 0 0 1-.504 0c-1.74-1.104-2.92-2.296-3.668-3.82-.748-1.517-1.055-3.328-1.055-5.679 0-.238.173-.428.394-.452a8.307 8.307 0 0 0 2.204-.747 9.985 9.985 0 0 0 2.078-1.43.452.452 0 0 1 .598 0 9.985 9.985 0 0 0 2.078 1.43 8.306 8.306 0 0 0 2.204.747c.22.024.394.214.394.452 0 2.351-.307 4.162-1.055 5.679"
                    fill-rule="evenodd"
                  ></path>
                </svg>
                <div class="card_item_statistic_value">20</div>
              </div>
            </div>
          </v-card>
        </v-card>
      </v-col>
    </div>
  </v-container>
</template>

<script>
export default {
  layout: 'tools',
  data() {
    return {
      cards: {
        shelter: {
          energy: 1,
          type: 'AQUATIC',
          damage: 0,
          shield: 115,
        },
        scale_dart: {
          energy: 1,
          type: 'AQUATIC',
          damage: 120,
          shield: 30,
        },
        swift_escape: {
          energy: 1,
          type: 'AQUATIC',
          damage: 110,
          shield: 20,
        },
        shipwreck: {
          energy: 1,
          type: 'AQUATIC',
          damage: 60,
          shield: 90,
        },
        aqua_vitality: {
          energy: 1,
          type: 'AQUATIC',
          damage: 80,
          shield: 40,
        },
        spinal_tap: {
          energy: 1,
          type: 'AQUATIC',
          damage: 100,
          shield: 20,
        },
        shell_jab: {
          energy: 1,
          type: 'AQUATIC',
          damage: 100,
          shield: 50,
        },
        deep_sea_gore: {
          energy: 1,
          type: 'AQUATIC',
          damage: 50,
          shield: 80,
        },
        clam_slash: {
          energy: 1,
          type: 'AQUATIC',
          damage: 110,
          shield: 40,
        },
        aquaponics: {
          energy: 1,
          type: 'AQUATIC',
          damage: 80,
          shield: 40,
        },
        heros_bane: {
          energy: 1,
          type: 'AQUATIC',
          damage: 120,
          shield: 30,
        },
        star_shuriken: {
          energy: 1,
          type: 'AQUATIC',
          damage: 115,
          shield: 10,
        },
        angry_lam: {
          energy: 1,
          type: 'AQUATIC',
          damage: 110,
          shield: 40,
        },
        swallow: {
          energy: 1,
          type: 'AQUATIC',
          damage: 80,
          shield: 30,
        },
        fish_hook: {
          energy: 1,
          type: 'AQUATIC',
          damage: 110,
          shield: 30,
        },
        crimson_water: {
          energy: 1,
          type: 'AQUATIC',
          damage: 120,
          shield: 30,
        },
        upstream_swim: {
          energy: 1,
          type: 'AQUATIC',
          damage: 110,
          shield: 30,
        },
        tail_slap: {
          energy: 0,
          type: 'AQUATIC',
          damage: 30,
          shield: 0,
        },
        black_bubble: {
          energy: 1,
          type: 'AQUATIC',
          damage: 110,
          shield: 40,
        },
        water_sphere: {
          energy: 1,
          type: 'AQUATIC',
          damage: 120,
          shield: 30,
        },
        flanking_smack: {
          energy: 1,
          type: 'AQUATIC',
          damage: 100,
          shield: 40,
        },
        chitin_jump: {
          energy: 1,
          type: 'AQUATIC',
          damage: 30,
          shield: 30,
        },

        sinister_strike: {
          name: 'Sinister Strike',
          energy: 1,
          type: 'BEAST',
          damage: 130,
          shield: 20,
        },

        nut_crack: {
          name: 'Nut Crack',
          energy: 1,
          type: 'BEAST',
          damage: 105,
          shield: 30,
        },
      },
    }
  },
}
</script>

<style>
.card_item_body {
  position: relative;
  background-color: #344829;
  border-radius: 25px;
  height: 340px;
}

.card_item_skill_name {
  position: absolute;
  color: #fff;
  justify-content: center;
  font-family: 'Changa One', cursive;
  display: flex;
  align-items: center;
  top: 19px;
  left: 60px;
  font-size: 17px;
  padding: 0 8px;
  text-align: center;
  height: 34px;
  width: 164px;
}

.card_item_energy {
  font-size: 30px;
  top: 6px;
  left: 6px;
  height: 56px;
  width: 56px;
  text-shadow: #83152b -2px 0, #83152b 0 2px, #83152b 2px 0, #83152b 0 -2px;
  position: absolute;
  color: #fff;
  justify-content: center;
  font-family: 'Changa One', cursive;
  display: flex;
  align-items: center;
}
.card_item_effect {
  color: #fff;
  position: absolute;
  bottom: 46.25px;
  left: 8.4px;
  width: 32px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card_item_effect_image {
  width: 50%;
  -o-object-fit: contain;
  object-fit: contain;
}

.card_item_description {
  color: #ccc;
  font-size: 11.5px;
  position: absolute;
  bottom: 0;
  left: 0;
  padding: 0 24px 0 48px;
  text-align: center;
  height: 122px;
  width: 100%;
  font-weight: 600;
}

.card_item_statistic {
  height: 54px;
  width: 54px;
  border-radius: 50%;
  background-color: #344829;
  display: flex;
  align-items: center;
  justify-content: center;
}

.card_item_statistic_wrapper {
  position: relative;
}

.card_item_statistic_icon,
.card_item__statistic_value {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.card_item_statistic_value {
  font-family: 'Changa One', cursive;
  font-size: 26px;
  color: #fff;
  text-shadow: #83152b -2px 0, #83152b 0 2px, #83152b 2px 0, #83152b 0 -2px;
}

.card_item_statistic_attack {
  position: absolute;
  top: 64px;
  left: -25px;
}

.card_item_statistic_defense {
  position: absolute;
  top: 124px;
  left: -25px;
}
</style>