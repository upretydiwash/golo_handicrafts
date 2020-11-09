<template>
  <div>
    <!-- <nuxt-link to="/" >  <h1 style="text-decoration:underline">My Blogs</h1> </nuxt-link>  -->

    <nuxt />
    <template>
      <div>
        <v-footer class="footer" dark padless>
          <v-card flat tile class="footer_card">
            <v-card-text>
              <v-btn
                v-for="icon in icons"
                :key="icon"
                class="mx-4 white--text"
                icon
              >
                <v-icon size="24px">
                  {{ icon }}
                </v-icon>
              </v-btn>
            </v-card-text>

            <v-card-text style="font-size:1.6rem;padding-left:15%;padding-right:15%" class="white--text pt-0">
              SGNP is dedicated in creating finest quality of Tibetan Handmade
              Rugs. Our team emphasizes on the uniqueness of the Tibetan
              knotting technique and on the purity of raw materials in creating
              a pleasing variation in both color and brilliance, making them the
              perfect and fashionable rugs.
            </v-card-text>

            <v-divider></v-divider>

            <v-card-text style="font-size:1.6rem" class="white--text">
© Copyright ShyiGaNyingPa Carpets 2016.            </v-card-text>
          </v-card>
        </v-footer>
      </div>
    </template>
  </div>
</template>

<script>
import footer from "../components/footer";
export default {
  components: {
    footer
  },

  data() {
    return {
      icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Welcome",
          to: "/"
        },
        {
          icon: "mdi-chart-bubble",
          title: "Inspire",
          to: "/inspire"
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js"
    };
  }
};
</script>
<style lang="scss">
.footer {
  text-align: center;
  height: 50vh;
  background: #111111 !important;
  font-family: "librebaskerville-regular", serif;
  ;
}
.footer_card {
  background: #111111 !important;
   
}

</style>
