<template>
  <Layout>
    <v-container fluid pt-6 mb-12 class="mobile-top">
      <v-row justify="center" align="center" v-for="section in sections" :key="section.node.id">
        <v-col cols="12" md="10" lg="5" px-4 mt-6>
          <v-img
            :src="section.node.featuredImage"
            max-height="500"
            alt="main image"
            class="mx-auto"
            contain
          ></v-img>
        </v-col>
        <v-col cols="12" md="10" lg="4" px-4 mb-12>
          <h1
            class="mont white--text text-center mt-6"
            style="font-size: 4em; font-weight: 400;"
          >{{ section.node.title }}</h1>
          <p
            class="subtitle-1 white--text mt-6"
            style="line-height: 2em;"
          >{{ section.node.paraOne }}</p>
          <p
            class="subtitle-1 white--text mt-6"
            style="line-height: 2em;"
          >{{ section.node.paraTwo }}</p>
          <v-row class="text-center">
            <v-col>
              <v-btn
                to="/store"
                x-large
                rounded
                clearable
                type="submit"
                class="highlight white--text mont headline px-8 mb-12"
                style="text-transform: none"
              >See the store</v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <v-container fluid highlight py-10 class="hero-background-circuit">
      <v-row justify="center">
        <v-col cols="12">
          <div style="padding: 60px 0px;">
            <h2
              class="text-center display-3 mont"
              style="line-height: 80px"
            >Gridsome is just what you need!</h2>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </Layout>
</template>

<page-query>
query {
  allHome {
    edges {
      node {
        id
        featuredImage
        title
        paraOne
        paraTwo
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: "Home"
  },
  computed: {
    sections() {
      return this.$page.allHome.edges;
    }
  }
};
</script>

<style lang="scss" scoped>
@media screen and (max-width: 1263px) {
  h3 {
    margin-top: 30px;
  }
}
@media screen and (max-width: 500px) {
  .text-container {
    padding: 0px 7px !important;
  }
  .v-card {
    padding: 10px 0px !important;
    margin-left: 0px !important;
    margin-right: 0px !important;
  }
  .description {
    padding-left: 5px !important;
    padding-right: 5px !important;
  }
  .mobile-top {
    padding: 10px 0 0 !important;
  }
}
.description {
  line-height: 1.7em !important;
}
@media screen and (min-width: 1400px) {
  .description {
    line-height: 1.9em !important;
    font-size: 1.5em !important;
  }
}
</style>