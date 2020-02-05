<template>
  <Layout>
    <v-container fluid px-0 pt-0>
      <v-row justify="space-around" mt-12>
        <v-col cols="12" lg="10" xl="8">
          <h1
            class="mont white--text text-center"
            style="font-size: 4vmax; font-weight: 400;"
          >Contact Us</h1>
          <v-divider class="mt-2 mb-6"></v-divider>
          <v-row justify="space-around">
            <v-col cols="12" sm="10" md="6">
              <v-hover>
                <v-card
                  class="mb-4 mygrey"
                  slot-scope="{ hover }"
                  :class="`elevation-${hover ? 12 : 1}`"
                >
                  <v-card-text>
                    <form
                      name="contact"
                      method="POST"
                      data-netlify="true"
                      data-netlify-honeypot="bot-field"
                      class="px-6 py-4"
                    >
                      <!-- NETLIFY FORM NAME -->
                      <input type="hidden" name="form-name" value="contact" />
                      <!-- NETLIFY BOT FIELD -->
                      <input type="text" name="bot-field" style="display: none;" />
                      <v-text-field
                        name="name"
                        label="Name"
                        prepend-inner-icon="perm_identity"
                        outlined
                        rounded
                        clearable
                        required
                        class="mb-1 form highlight--text"
                      ></v-text-field>
                      <v-text-field
                        type="email"
                        name="email"
                        label="Email"
                        prepend-inner-icon="mail_outline"
                        outlined
                        rounded
                        clearable
                        required
                        class="my-1 form highlight--text"
                      ></v-text-field>

                      <v-textarea
                        name="message"
                        label="Message"
                        prepend-inner-icon="message"
                        rows="4"
                        outlined
                        rounded
                        clearable
                        required
                        class="my-1 form highlight--text"
                      ></v-textarea>
                      <div class="text-center">
                        <v-btn
                          x-large
                          rounded
                          clearable
                          type="submit"
                          class="highlight white--text px-10"
                        >Submit</v-btn>
                      </div>
                    </form>
                  </v-card-text>
                </v-card>
              </v-hover>
            </v-col>
            <v-col cols="12" md="6" lg="5">
              <div class="my-8">
                <div class="text-left">
                  <a href="mailto:contact@vowaidfoundation.org">
                    <v-row justify="center" class="pb-6">
                      <v-col cols="3" class="text-center">
                        <v-icon size="45px" class="highlight--text">fas fa-envelope</v-icon>
                      </v-col>
                      <v-col cols="9">
                        <h4 class="white--text display-1">Send an email</h4>
                        <p class="white--text subtitle-1">contact@vowaidfoundation.org</p>
                      </v-col>
                    </v-row>
                  </a>
                </div>
                <div class="text-xs-left">
                  <a href="tel:781-486-3408">
                    <v-row justify="center" class="pb-6">
                      <v-col cols="3" class="text-center">
                        <v-icon size="45px" class="highlight--text">fas fa-mobile-alt</v-icon>
                      </v-col>
                      <v-col cols="9">
                        <h4 class="white--text display-1">Give us a ring</h4>
                        <p class="white--text subtitle-1">(781) 486-3408</p>
                      </v-col>
                    </v-row>
                  </a>
                </div>
                <div class="text-xs-left">
                  <v-row justify="center" class="pb-6">
                    <v-col cols="3" class="text-center">
                      <v-icon size="45px" class="highlight--text">fas fa-map-marked-alt</v-icon>
                    </v-col>
                    <v-col cols="9">
                      <h4 class="white--text display-1">
                        <span class="hide-on-mobile">Mailing</span> Address
                      </h4>
                      <p class="white--text subtitle-1">
                        2307 S. Rural Road
                        <br />Tempe, Arizona 85282
                      </p>
                    </v-col>
                  </v-row>
                </div>
              </div>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </Layout>
</template>

<script>
export default {
  data() {
    return {
      name: "contact"
    };
  },
  metaInfo: {
    title: "Contact Us"
  }
};
</script>