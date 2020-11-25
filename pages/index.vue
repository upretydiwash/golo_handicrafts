<template>
  <div id="app" >
    <!-- Home -->
    <div id="home">
      <div class="overlay ">
        <v-app-bar  dark class="nav_bar">
          <div></div>
          <v-toolbar-title
          
            ><img
              src="../static/uploads/logo.jpg"
              height="100"
              width="150"
              style="max-height:auto;min-width:auto,"
          /></v-toolbar-title>
          <v-spacer />
          <div class="appbar_content">
             <v-btn href="#home">HOME</v-btn> 
             <v-btn href="#about">ABOUT</v-btn> 
             <v-btn href="#product"> COLLECTION</v-btn> 
             <v-btn href="#contact">CONTACT</v-btn> 
          </div>
        </v-app-bar>

        <template>
          <div class="overlay">
            <v-parallax
              height="800"
              class="overlay"
              :src="require('../assets/cover.jpg')"
            >
              <div v-if="bar">
                <v-card> HELLO</v-card>
              </div>

              <div class="cover_text ">
                <!-- <img
                src="../static/uploads/logo.jpg"
                height="150"
                width="150"
                alt=""
              /> -->
                <h1 v-html="covertext">
                </h1>
              </div>
              <div class="btn_cover">
                <v-btn height="50px" width="150px" outlined href="#about"
                  >LEARN MORE</v-btn
                >
              </div>
            </v-parallax>
          </div>
        </template>
      </div>
    </div>

    <!--About div -->
    <div class="overlay">
    <div class="about_us " id="about">
      <div class="container">
        <h2 style="margin-top:5rem">
          ABOUT US
        </h2>
        <p v-html="about">
          
        </p>
      </div>
    </div>
</div>
    <!-- Product Div -->
    <div class="products" id="product">
      <div class="container">
        <div class="text_products">
          <h3>COLLECTIONS</h3>
          <h1 v-html="collectiontext"></h1>

          <div style="margin-top:2%; margin:2%;padding:2%">
            <v-row>
              <v-col
                cols="6"
                
                v-for="article in articles"
                :key="article.id"
              >
                <div class="pro_card container" data-app >
                  <!-- <v-card-title> -->
                  <!-- {{ article.description }}</v-card-title> -->
                  <img 
                    :src="article.img"
                    class="responsive"
                                        @click.stop="dialog = true"

                  />
                  <!-- <div class="middle">
                    <div class="text">{{ article.description }}</div>
                  </div> -->
                    <!-- <v-dialog v-model="dialog" max-width="290">
                  <v-card>
                    <v-card-title class="headline">
                      Use Google's location service?
                    </v-card-title>

                    <v-card-text>
                      Let Google help apps determine location. This means
                      sending anonymous location data to Google, even when no
                      apps are running.
                    </v-card-text>

                    <v-card-actions>
                      <v-spacer></v-spacer>

                      <v-btn
                        color="green darken-1"
                        text
                        @click="dialog = false"
                      >
                        Disagree
                      </v-btn>

                      <v-btn
                        color="green darken-1"
                        text
                        @click="dialog = false"
                      >
                        Agree
                      </v-btn>
                    </v-card-actions>
                  </v-card>
                </v-dialog> -->
              
                </div>
                
                
              </v-col>
            </v-row>
          </div>
        </div>
      </div>
    </div>

    <!-- Contact us -->
    <div class="overlay">
    <div class="contact " id="contact">
      <div class="container text_contact ">
        <h3>Contact</h3>
        <h1>Get In Touch.</h1>
      </div>
      <v-row>
        <v-col>
          <div class="form_cont center">
            <v-form class="form_cont" netlify="true">
              <v-container class="form_container">
                <p style="align-text:center">SEND US A MESSAGE</p>
                <v-row>
                  <v-col cols="6">
                    <input
                      class="col"
                      type="text"
                      color="white"
                      placeholder="Name"
                      outlined
                      label="Name"
                      required
                    />
                  </v-col>
                </v-row>

                <v-row>
                  <v-col cols="3">
                    <input class="col" outlined placeholder="Email" required />
                  </v-col>
                  <v-col cols="3">
                    <input
                      class="col"
                      outlined
                      placeholder="Subject"
                      required
                    />
                  </v-col>
                </v-row>

                <v-row>
                  <v-col cols="6">
                    <textarea
                      class="col"
                      type="message"
                      outlined
                      placeholder="Message"
                    />
                  </v-col>
                </v-row>

                <v-row>
                  <v-col cols="6">
                    <v-btn block class="btn_submit">Submit</v-btn>
                  </v-col>
                </v-row>
              </v-container>
            </v-form>
          </div>
        </v-col>
      </v-row>
    </div>
</div>
    <template>
      <v-footer
        style="text-align:center; margin:0px; padding:0px; background:black "
        :padless="padless"
      >
        <v-card flat dark tile width="100%" class="red lighten-1 text-center">
          <v-card-text>
            <v-btn v-for="icon in icons" :key="icon" class="mx-4" icon>
              <v-icon size="24px">
                {{ icon }}
              </v-icon>
            </v-btn>
          </v-card-text>

          <v-divider></v-divider>

          <v-card-text class="white--text">
            Copyright © GOLO Handicrafts 2020.
          </v-card-text>
        </v-card>
      </v-footer>
    </template>
  </div>
</template>

<script>
import contactform from "../components/contactform";
import footer from "../components/footer";
import about from '../content/post/about.md';
import covertext from '../content/post/covertext.md';
import collectiontext from '../content/post/collectiontext.md'
import logo from '../content/post/logo.md'
export default {
  el:'#app',
  
  async asyncData(context) {
    const { $content } = context;
    const articles = await $content("product").fetch();

    return {
      articles
    };
  },
  computed:{
about(){
  return about
  console.log(about)
},
covertext(){
  return covertext
},
collectiontext(){
  return collectiontext
},
logo()
{
  return logo
}

  },

  components: {
    contactform,
    footer
  },
  data() {
    return {
      bar: false,
      dialog: false,
      padless: false,
      icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
      width: this.a
    };
  },
  methods: {
    openNav() {
      document.getElementById("mySidenav").style.width = "250px";
    },

    closeNav() {
      document.getElementById("mySidenav").style.width = "0";
    },
    getInnerWidth(){
      var a = window.innerWidth
      this.width = a
      
    }
  }
};
</script>
<style lang="scss">
// .content {
//   text-align: center;
//   background-position: fixed;
//   font-size: xxx-large;

//   background-attachment: fixed;
//   background-size: cover;
// }
.v-parallax_content {
  height: 200vh !important;
  width: 100%;
  opacity: 1;
  overflow: hidden;
  position: relative;
}

.overlay {
  /* Permalink - use to edit and share this gradient: http://colorzilla.com/gradient-editor/#6b4da8+0,4977c2+100&0.85+0,0.85+100 */
opacity: 1;
  background: -moz-linear-gradient(
    left,
    rgba(107, 77, 168, 0.85) 0%,
    rgba(73, 119, 194, 0.85) 100%
  ); /* FF3.6-15 */
  background: -webkit-linear-gradient(
    left,
    rgba(107, 77, 168, 0.85) 0%,
    rgba(73, 119, 194, 0.85) 100%
  ); /* Chrome10-25,Safari5.1-6 */
  background: linear-gradient(
    to right,
    rgba(107, 77, 168, 0.85) 0%,
    rgba(73, 119, 194, 0.85) 100%
  ); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#d96b4da8', endColorstr='#d94977c2', GradientType=1 ); /* IE6-9 */
}
.centered {
  position: relative;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  visibility: hidden;
}
.nav_item a {
  text-align: center !important;
  align-content: center;
  padding: 10px;
  margin: 10px;
}
.cover_card {
  align-items: center;
  text-align: center;
  color: grey !important;
}

.appbar_content {
  background: transparent !important;
  background-color: Transparent;
  background-repeat: no-repeat;
  border: none;
  cursor: pointer;
  overflow: hidden;
}
.form_container {
  margin-left: 25%;
}
// div:nth-child(5) {
//   background-image: url("../assets/hello.jpeg");
// }
.pro_card {
  cursor: pointer;
  text-align: center !important;
}
.pro_card div{
  text-align: center;
}
.pro_card:hover .centered {
  position: relative;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
a {
  text-decoration: none;
}
.nav_bar {
  align-content: center;
  text-align: center;
}

.home {
  height: 150vh;
}

// .img{
//   height: 100vh;
// }
.about_us {
  font-family: "montserrat-bold", sans-serif;
  text-align: center;
    // background: #e9e9e9;

  color: white;
  min-height: 100vh;
  height: max-content;
}
.about_us p {
  font-family: "librebaskerville-bold", serif;
  font-size: 3rem;
  line-height: 1.8;
  color: white;
  margin-top: 5rem;
}
.cover_text {
  text-align: center;
  font-family: "montserrat-bold", sans-serif;
  font-size: 2.2rem;
  color: white;
  text-transform: uppercase;
  margin-top: -5% !important;
  letter-spacing: 0.3rem;
  margin: 0 0 0.9rem 0;
  padding: 10%;
}

.logo {
  display: block;

  margin: 0;
  padding: 0;
  outline: 0;
  border: none;
  width: 190px;
  height: 37px;
  margin-top: -20%;
  background-size: 190px 65px;
  font: 0/0 a;
  text-shadow: none;
  color: transparent;
  transition: all 0.5s ease-in-out;
}
.btn_cover {
  align-content: center;
  text-align: center;
  margin-top: -10%;
  background: transparent !important;
}

.theme--light.v-btn {
  color: white;
}
.form_cont {
}
.products {
  background: #e9e9e9;
  align-content: center;
  text-align: center;
  color: black;
  min-height: 100vh;
  height: max-content;
}
.products h3,
.text_contact h3 {
  color: black;
  font-family: "montserrat-bold", sans-serif;
  font-size: 1.8 rem;
  line-height: 1.667;
  // color: rgba(242, 242, 242, 0.5);
  text-transform: uppercase;
  letter-spacing: 0.3rem;
  margin-bottom: 1.2rem;
}
.text_contact h3 {
  color: white !important;
}
.products h1 {
  color: black;
  font-family: "librebaskerville-bold", serif;
  font-size: 2.8rem;
  line-height: 1.375;
  display: block;
  padding-left: 17%;
  padding-right: 17%;
}
.text_products {
  color: #000000;
  padding: 8%;
  justify-content: center;
}
.text_contact {
  align-content: center;
  text-align: center;
}
.text_contact h1 {
  font-family: "librebaskerville-bold", serif;
  font-size: 2.8rem;
  line-height: 1.375;
  display: block;
}
.contact {
  /* Permalink - use to edit and share this gradient: http://colorzilla.com/gradient-editor/#6b4da8+0,4977c2+100&0.85+0,0.85+100 */
  color: white;
  padding: 7%;
  align-content: center !important;
  align-items: center;
  height: 100vh;
  justify-items: center;
}

.menu {
  font-size: 30px;
  cursor: pointer;
  margin-top: -10% !important;
  float: right;
  position: fixed;
  background: rgba(0, 0, 0, 0.4);
}
.menu_btn {
  background: transparent !important;
  height: 42px !important;
  margin-top: -20%;

  float: right;
  position: fixed;
  display: block;
}
.sidenav {
  height: 100%;
  width: 0;

  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #111;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
}

.sidenav a {
  padding: 8px 8px 8px 32px;
  text-decoration: none;
  font-size: 25px;
  color: #818181;
  display: block;
  transition: 0.3s;
}

.sidenav a:hover {
  color: #f1f1f1;
}

.sidenav .closebtn {
  position: absolute;
  top: 0;
  right: 25px;
  font-size: 36px;
  margin-left: 50px;
}
.responsive {
  width: 100%;
  opacity: 1;
  height: auto;
  max-height: 250px;
  display: block;
  max-width: 350px;
  transition: transform 0.2s;
}
// .middle {
//   transition: 0.5s ease;
//   opacity: 0;

//   top: 50%;
//   left: 50%;
//   transform: translate(-50%, -50%);
//   -ms-transform: translate(-50%, -50%);
//   text-align: center !important;
// }
// .middle > div {
//   text-align: center !important;
// }
// .pro_card:hover .responsive {
//   opacity: 0.3;
// }

// .pro_card:hover .middle {
//   opacity: 1;
//   align-content: center;
//   text-align: center !important;
// }

// .text {
//   // background-color: #4CAF50;
//   color: black;
//   text-transform: uppercase;
//   font-size: 16px;
//     font-family: "montserrat-bold", sans-serif;

//   // padding: 16px 32px;
//   // margin-left: 50%;
//   // margin-right: 50%;
// }
.responsive:hover {
  transform: scale(1.2);
  transition-delay: 0.1ms;
  
}

@media screen and (max-height: 450px) {
  .sidenav {
    padding-top: 15px;
  }
  .sidenav a {
    font-size: 18px;
  }
}
html {
  scroll-behavior: smooth;
}
.form_contact {
  align-items: center;
  float: center;
  align-self: center;
}
.btn_submit {
  background: transparent !important;
  font-size: 1.5rem;
  display: block;
  letter-spacing: 0.2rem;
  height: 6rem;
  line-height: 6rem;
  padding: 0 3rem;
  width: 100%;
  background: #f9a828;
  color: #000000;
  margin-top: 0.6rem;
}

v-form h3 {
  font-size: 1.4rem;
  line-height: 1.7;
  text-transform: uppercase;
  letter-spacing: 0.2rem;
}

v-text-field {
  border: white !important;
  color: white !important;
}
v-form input,
textarea {
  background: white !important;
}
input,
v-textarea {
  background: white !important;
}
@media only screen and (min-width: 150px) {
  h1,
  .products h1,
  .contact h1 {
    font-size: 30px;
  }
  h3 {
    font-size: 30px;
  }

  .about_us p {
    font-size: 25px;
  }
  .menu {
    font-size: 30px;
    cursor: pointer;
    margin-top: -10%;
    float: right;
    position: fixed;
    background: rgba(0, 0, 0, 0.4);
  }
  img {
    max-width: auto;
    max-height: auto;
    min-width: auto;
    min-height: auto;
  }
  v-card:hover {
    cursor: pointer;
  }
}
@media only screen and (max-width: 600px) {
  .nav_bar v-btn {
    width: 30px !important;
  }
}
</style>
