<template>
  <div>
    <!-- firstdiv -->
    <div>
      <div class="cover">
        <template>
          <v-parallax
            height="800"
            style="max-width:100%"
            :src="require('../assets/cover.jpg')"
          >
            <div>
              <span class="menu" @click="openNav()"> MENU &#9776;</span>
            </div>
            <div id="mySidenav" class="sidenav" close-on-content-click>
              <a href="javascript:void(0)" class="closebtn" @click="closeNav()"
                >&times;</a
              >
              <a href="#" @click="closeNav()">Home</a>
              <a href="#about" @click="closeNav()">About</a>
              <a href="#product" @click="closeNav()">Collection</a>
              <a href="#contact" @click="closeNav()">Contact</a>
            </div>
            <div v-if="bar">
              <v-card> HELLO</v-card>
            </div>

            <div class="cover_text">
              <img
                src="../static/uploads/logo.jpg"
                height="150"
                width="150"
                alt=""
              />
              <h1>
                Authentic handmade felt.
              </h1>
            </div>
            <div class="btn_cover">
              <v-btn height="50px" width="150px" outlined href="#about"
                >LEARN MORE</v-btn
              >
            </div>
          </v-parallax>
        </template>
      </div>
    </div>

    <!--About div -->
    <div class="about_us" id="about">
      <div class="container">
        <h2 style="margin-top:5rem">
          ABOUT US
        </h2>
        <p>
          SGNP is dedicated in creating finest quality of Tibetan Handmade Rugs.
          Our team emphasizes on the uniqueness of the Tibetan knotting
          technique and on the purity of raw materials in creating a pleasing
          variation in both color and brilliance, making them the perfect and
          fashionable rugs.
        </p>
      </div>
    </div>

    <!-- Product Div -->
    <div class="products" id="product">
      <div class="container">
        <div class="text_products">
          <h3>COLLECTIONS</h3>
          <h1>See Our Featured Carpets and Rugs.</h1>

          <div style="margin-top:2%; margin:2%;padding:2%">
           
              <v-row   >
                <v-col cols="6" v-for="article in articles" :key="article.id">
                  <v-card dark class="pro_card">
                    <v-card-title>
                  {{ article.description }}</v-card-title>
                  <v-img :src="article.img"/>
                   </v-card>
                </v-col>
              </v-row>
            
            <img src="../static/uploads/ball.jpg" height="100px" />
          </div>
          
        </div>
      </div>
    </div>

    <!-- Contact us -->
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
export default {
  async asyncData(context) {
    const { $content } = context;
    const articles = await $content("product").fetch();

    return {
      articles
    };
  },

  components: {
    contactform,
    footer
  },
  data() {
    return {
      bar: false,
      padless:false,
      icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"]
    };
  },
  methods: {
    openNav() {
      document.getElementById("mySidenav").style.width = "250px";
    },

    closeNav() {
      document.getElementById("mySidenav").style.width = "0";
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
}
.form_container {
  margin-left: 25%;
}
// div:nth-child(5) {
//   background-image: url("../assets/hello.jpeg");
// }
.pro_card{
  cursor: pointer;
  
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
  background: #eeecec;

  color: #07617d;
  min-height: 100vh;
  height: max-content;
}
.about_us p {
  font-family: "librebaskerville-bold", serif;
  font-size: 3rem;
  line-height: 1.8;
  color: #2e383f;
  margin-top: 5rem;
}
.cover_text {
  text-align: center;
  font-family: "montserrat-bold", sans-serif;
  font-size: 2.2rem;
  color: white;
  text-transform: uppercase;
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
  background: rgb(152, 150, 150);
  align-content: center;
  text-align: center;
  color: white;
  min-height: 100vh;
  height: max-content;
}
.products h3,
.text_contact h3 {
  color: rgba(242, 242, 242, 0.5);
  font-family: "montserrat-bold", sans-serif;
  font-size: 1.8 rem;
  line-height: 1.667;
  color: rgba(242, 242, 242, 0.5);
  text-transform: uppercase;
  letter-spacing: 0.3rem;
  margin-bottom: 1.2rem;
}
.products h1 {
  color: #ffffff;
  font-family: "librebaskerville-bold", serif;
  font-size: 2.8rem;
  line-height: 1.375;
  display: block;
  padding-left: 17%;
  padding-right: 17%;
}
.text_products {
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
  background: rgb(17, 16, 16);
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
  background: #f9a828 !important;
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
  v-card:hover
  {
    cursor: pointer;
  }
}
</style>
