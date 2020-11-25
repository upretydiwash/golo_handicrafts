<template>
  <div>
    <!-- <nuxt-link to="/" >  <h1 style="text-decoration:underline">My Blogs</h1> </nuxt-link>  -->

  
  
    <nuxt />
    
   <footer/>
  </div>
</template>

<script>
import footer from "../components/footer";
export default {
  inject: {
      theme: {
        default: { isDark: false },
      },
    },
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
  },
  mounted() {
window.onload    
  },
};
</script>

<style lang="scss">
.footer {
  text-align: center;
  align-content: center !important;
  height: 50vh;
  background: #111111 !important;
  font-family: "librebaskerville-regular", serif;
}
.footer_card {
  background: #111111 !important;
}
</style>
