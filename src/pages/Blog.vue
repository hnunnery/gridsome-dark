<template>
  <Layout>
    <v-container fluid class="text-container">
      <v-row justify="center">
        <v-col
          cols="12"
          lg="10"
          my-6
          v-for="post in posts"
          :key="post.node.id"
          @click="onClick(post)"
          style="cursor: pointer;"
        >
          <v-hover>
            <v-card
              slot-scope="{ hover }"
              :class="`elevation-${hover ? 16 : 6}`"
              class="pa-6 mx-6 mygrey"
            >
              <v-row justify="space-around" align="center">
                <v-col cols="12" sm="10" md="8" lg="5" class="px-4">
                  <v-img
                    v-if="post.node.featuredImage != null"
                    :src="post.node.featuredImage"
                    alt="blog"
                    aspect-ratio="1.7778"
                    lazy-src
                  ></v-img>
                </v-col>
                <v-col cols="12" lg="7" xl="6" class="text-center px-2">
                  <h3 class="display-1 white--text">{{ post.node.title }}</h3>
                  <v-divider class="mt-2 mb-4 mx-6"></v-divider>
                  <v-col cols="12" md="6">
                    <p class="title font-weight-bold">
                      <v-icon
                        size="25px"
                        class="mr-2 hidden-sm-and-down highlight--text"
                      >fas fa-calendar-alt</v-icon>
                      {{ post.node.date_ }}
                    </p>
                  </v-col>
                  <p
                    v-html="post.node.preview"
                    class="subtitle-2 text-left white--text description px-6"
                  ></p>
                </v-col>
              </v-row>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
  </Layout>
</template>

<page-query>
query {
  allPost {
    totalCount
    edges {
      node {
        id
        title
        path
        date_
        content
        preview
        featuredImage
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: "Blog"
  },
  computed: {
    posts() {
      return this.$page.allPost.edges;
    }
  },
  methods: {
    onClick(post) {
      this.$router.push({ path: post.node.path });
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