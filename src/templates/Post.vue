<template>
  <Layout>
    <v-container fluid ma-0 pa-0>
      <v-row justify="center" my-5>
        <v-col cols="12" md="10" lg="8" xl="6">
          <v-img
            :src="$page.post.featuredImage"
            alt="blog"
            max-width="900"
            aspect-ratio="1.7778"
            lazy-src
            class="mx-auto elevation-12"
          ></v-img>
          <h1 class="display-2 mt-5 mb-2 mx-3 text-center white--text">{{ $page.post.title }}</h1>
          <v-divider class="ma-3"></v-divider>
          <p class="subheading text-xs-left mx-3 white--text">{{ $page.post.date_ }}</p>
          <div v-html="$page.post.content" class="markdown-body text-xs-left mx-3 white--text" />
        </v-col>
      </v-row>
    </v-container>
  </Layout>
</template>

<page-query>
query Post ($path: String!) {
  post: post (path: $path) {
    title
    content
    featuredImage
    date_
    preview
    path
  }
}
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.post.title,
      meta: [
        {
          key: "description",
          name: "description",
          content: this.$page.post.preview
        },
        {
          key: "og:title",
          property: "og:title",
          content: this.$page.post.title
        },
        {
          key: "og:description",
          property: "og:description",
          content: this.$page.post.preview
        },
        {
          key: "og:image",
          property: "og:image",
          content: this.$page.post.featuredImage
        },
        {
          key: "og:url",
          property: "og:url",
          content: `https://gridsomeexample.netlify.com${this.$page.post.path}`
        },
        {
          key: "og:type",
          property: "og:type",
          content: "article"
        },
        {
          key: "twitter:card",
          name: "twitter:card",
          content: "summary_large_image"
        }
      ]
    };
  }
};
</script>
<style lang="scss" scoped>
@media screen and (max-width: 959px) {
  .row {
    margin-top: 0px !important;
  }
}
</style>