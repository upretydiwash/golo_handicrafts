<template>
  <div>
    <!-- firstdiv -->
    <div>
      <div class="cover">
        <template>
          <v-parallax height="800" :src="require('../assets/cover.jpg')">
            <img class="logo" style="float:right" src="../assets/logo.png" /><img />

            <div class="menu">
              <span
                style="font-size:30px;cursor:pointer;float:right;position:fixed;background:rgba(0,0,0, 0.4);"
                @click="openNav()"
              >
                MENU &#9776;</span
              >
            </div>
            <div id="mySidenav" class="sidenav" close-on-content-click>
              
              <a href="javascript:void(0)" class="closebtn" @click="closeNav()"
                >&times;</a
              >
              <a href="#" @click="closeNav()">Home</a>
              <a href="#about" @click="closeNav()" >About</a>
              <a href="#product" @click="closeNav()">Collection</a>
              <a href="#contact" @click="closeNav()">Contact</a>
            </div>
            <div v-if="bar">
              <v-card> HELLO</v-card>
            </div>

            <div class="cover_text">
              <h3>
                WE ARE SHYIGANYINGPA CARPETS.
              </h3>
              <h1>
                We Craft Authentic Handmade Tibetan Carpets.
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
        <h2>
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
      <div class="container ">
        <div class="text_products">
          <h3>COLLECTIONS</h3>
          <h1>See Our Featured Carpets and Rugs.</h1>
        </div>
      </div>
    </div>
    <div class="extra">
      <div class="container"></div>
    </div>

    <!-- Contact us -->
    <div class="contact " id="contact">
      <div class="container text_contact ">
        <h3>Contact</h3>
        <h1>Get In Touch.</h1>
      </div>
      <v-row
        ><v-col cols="6"><contactform /></v-col>
        <!-- <v-col cols="6">
         <div class="col-md-3 col-md-offset-1 contact-info">
          <div class="contact-item">
            <h3>Contact Information</h3>
            <p>
              <span><i class="fa fa-map-marker"></i> WHERE TO FIND US</span>
              Hattisar,<br />
              Kathmandu, Nepal
            </p>
          </div>
          <div class="contact-item">
            <p>
              <span><i class="fa fa-envelope-o"></i> Email</span>
              info@level9.tech
            </p>
          </div>
        </div>
        <div class="col-md-12">
          <div class="row">
            <div class="social">
              <ul>
                <li>
                  <a href="https://www.facebook.com/level9.tech" target="blank"
                    ><i class="fa fa-facebook"></i
                  ></a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </v-col> -->
      </v-row>
    </div>
  </div>
</template>
<script>
import contactform from "../components/contactform";

export default {
  components: {
    contactform
  },
  data() {
    return {
      bar: false
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

// div:nth-child(5) {
//   background-image: url("../assets/hello.jpeg");
// }
.home {
  height: 150vh;
}
// .img{
//   height: 100vh;
// }
.about_us {
  font-family: "montserrat-bold", sans-serif;
  text-align: center;

  margin-top: 2rem;
  color: #07617d;
  height: 100vh;
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
.products {
  background: black;
  align-content: center;
  text-align: center;
  color: white;
  height: 100vh;
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
  margin-top: 2%;
  background: black;
  color: white;
  padding: 7%;
}
.extra {
  height: 50vh;
}
// .menu{
//   align-content: right !important;
//   font-size:42px !important ;
//   text-align: right;
//   background: transparent !important;
//   height: 42px !important;
//   float: right;
//   // position: fixed;
//   // display: flex;
//   display: block;
//   position: absolute;
//   display: fixed;

//   flex-wrap: nowrap;
// }
.menu_btn {
  background: transparent !important;
  height: 42px !important;

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
</style>
