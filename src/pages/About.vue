<template>
  <Layout>
    <v-container pt-0>
      <v-row justify="center">
        <v-col cols="12" md="10" px-4>
          <h1 class="mont white--text text-center" style="font-size: 4vmax;">About us</h1>
          <v-divider class="mt-2 mb-6"></v-divider>
          <p
            class="subtitle-1 white--text"
          >Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error doloremque omnis animi, eligendi magni a voluptatum, vitae, consequuntur rerum illum odit fugit assumenda rem dolores inventore iste reprehenderit maxime! Iusto.</p>
        </v-col>
      </v-row>
    </v-container>
  </Layout>
</template>

<script>
export default {
  data() {
    return {
      name: "about"
    };
  },
  metaInfo: {
    title: "About us"
  }
};
</script>

