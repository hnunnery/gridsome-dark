  
<template>
  <v-app style="background-color: #2a2a2e !important;">
    <v-app-bar app absolute elevation="0" class="app transparent">
      <v-dialog v-model="dialog" fullscreen hide-overlay transition="dialog-bottom-transition">
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on" class="hidden-md-and-up mr-0">
            <v-icon class="white--text">fas fa-bars</v-icon>
          </v-btn>
        </template>
        <v-card class="mygrey">
          <v-toolbar class="mont mygrey">
            <v-toolbar-title class="mont white--text">{{ $static.metadata.siteName }}</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn icon class="white--text" style="font-size: 1.7em;" @click="dialog = false">X</v-btn>
          </v-toolbar>
          <v-container fluid ma-0 pt-6 style="min-height: 100vh;">
            <v-row justify="center" py-6>
              <v-col cols="6" class="text-center">
                <g-link to="/">
                  <v-icon size="80px" class="highlight--text">fas fa-home</v-icon>
                  <p class="white--text display-1 mt-4">Home</p>
                </g-link>
              </v-col>
              <v-col cols="6" class="text-center">
                <g-link to="/store">
                  <v-icon size="80px" class="highlight--text">fas fa-store</v-icon>
                  <p class="white--text display-1 mt-4">Store</p>
                </g-link>
              </v-col>
              <v-col cols="6" class="text-center">
                <g-link to="/about">
                  <v-icon size="80px" class="highlight--text">fas fa-users</v-icon>
                  <p class="white--text display-1 mt-4">About</p>
                </g-link>
              </v-col>
              <v-col cols="6" class="text-center">
                <g-link to="/blog">
                  <v-icon size="80px" class="highlight--text">fas fa-blog</v-icon>
                  <p class="white--text display-1 mt-4">Blog</p>
                </g-link>
              </v-col>
              <v-col cols="6" class="text-center">
                <g-link to="/contact">
                  <v-icon size="80px" class="highlight--text">fas fa-at</v-icon>
                  <p class="white--text display-1 mt-4">Contact</p>
                </g-link>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-dialog>
      <v-container>
        <v-row class="align-center">
          <v-col class="text-center text-md-left">
            <g-link to="/">
              <v-toolbar-title
                class="white--text mont"
                style="font-size: 1.8em;"
              >{{ $static.metadata.siteName }}</v-toolbar-title>
            </g-link>
          </v-col>
          <!-- NAVBAR FOR bold AND UP SCREEN SIZES -->
          <v-toolbar-items class="hidden-sm-and-down">
            <v-btn text to="/" class="nav-text py-2 white--text">Home</v-btn>
            <v-btn text to="/store" class="nav-text py-2 white--text">Store</v-btn>
            <v-btn text to="/about" class="nav-text py-2 white--text">About</v-btn>
            <v-btn text to="/blog" class="nav-text py-2 white--text">Blog</v-btn>
            <v-btn text to="/contact" class="nav-text py-2 white--text">Contact</v-btn>
          </v-toolbar-items>
          <!-- shopping cart icon on non-mobile devices -->
          <v-btn fab dark color="highlight" class="snipcart-checkout hidden-sm-and-down">
            <v-icon dark>fas fa-shopping-cart</v-icon>
          </v-btn>
          <!-- shopping cart icon on mobile devices -->
        </v-row>
      </v-container>
      <v-btn icon class="snipcart-checkout hidden-md-and-up">
        <v-icon class="highlight--text">fas fa-shopping-cart</v-icon>
      </v-btn>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-content>
      <!-- Provides the application the proper gutter -->
      <v-container fluid>
        <!-- If using vue-router -->
        <slot></slot>
      </v-container>
    </v-content>

    <v-footer app absolute color="#1C1C1C" class="page-footer">
      <v-row justify="space-around">
        <v-col cols="auto" class="text-center footer-text">
          <p class="white--text">
            Created by
            <a href="https://www.codehunter.io" target="_blank">
              <span class="b-align">code</span>
              <span class="white--text font-weight-bold">Hunter</span>
            </a> Web Design and Development
          </p>
        </v-col>
        <v-col cols="auto">
          <p class="white--text body-2">© 2019 {{ $static.metadata.siteName }} | All Rights Reserved</p>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
export default {
  name: "app",
  data() {
    return {
      dialog: false,
      clipped: false,
      drawer: true,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js"
    };
  }
};
</script>

<style lang="scss" scoped>
.navbar-icons {
  padding-top: 13px;
}
.nav-font-size {
  font-size: 1.5em;
}
.nav-text {
  font-size: 1.7em;
  font-weight: 400;
  font-family: "Montserrat", sans-serif !important;
  text-transform: capitalize;
  margin: 0 10px;
}
// NAVBAR - raising fontawesome5 icons
.fa,
.fab,
.fal,
.far,
.fas {
  @media only screen and (max-width: 958px) {
    vertical-align: text-top;
  }
}
/* STYLE NAVIGATION DRAWER */
.v-list {
  padding: 50px 0 0 !important;
}
// FOOTER - bottom aligns text in codeHunter
.b-align {
  vertical-align: bottom;
  line-height: 15px;
  color: #22aa00;
  font-size: 0.85em;
  margin-right: 0.5px;
}
.page-footer {
  /* border-top: 1px solid #2a2968; */
  p {
    margin: 0px auto;
  }
}
.footer-text {
  font-size: 0.8em;
}
</style>

<style lang="scss">
@import url("https://cdnjs.cloudflare.com/ajax/libs/github-markdown-css/3.0.1/github-markdown.min.css");
.markdown-body {
  box-sizing: border-box;
  min-width: 200px;
  max-width: 1000px;
  margin: 0 auto;
}
a {
  text-decoration: none !important;
  color: #1c1c1c !important;
}
.subtitle-1 {
  font-size: 1.3em !important;
}
.mont {
  font-family: "Montserrat", sans-serif;
}
.v-btn {
  transition: all 0.2s ease-in-out;
}
.v-btn:hover {
  transform: scale(1.1);
}
.v-card {
  border-radius: 15px !important;
}

/* SNIPCART CUSTOM STYLES */
.snipcart-modal,
.snipcart-modal__container,
.snipcart-cart-header,
.snipcart-cart__content,
.snipcart-item-line,
.snipcart-item-list,
.snipcart-cart__footer,
.snipcart-discount-box,
.snipcart__box,
.snipcart-cart-summary,
.snipcart-cart-summary__content,
.snipcart-cart__secondary-header {
  background-color: #2a2a2e !important;
}
.snipcart-item-line {
  box-shadow: 0 8px 24px #424242 !important;
}
.snipcart__button--icon {
  border: #2a2a2e !important;
}
.snipcart-modal,
.snipcart-modal__close-title,
.snipcart-item-quantity__label,
.snipcart-item-quantity__quantity-price-container,
.snipcart-cart-summary-fees,
.snipcart-form__label,
.snipcart-cart-summary-item,
.snipcart-form__field,
#snipcart-payment-form__input {
  color: #f9f9fa !important;
}
.snipcart__box--badge {
  background-color: #4a9df8 !important;
  color: #f9f9fa !important;
}
</style>
