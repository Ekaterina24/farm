<template>
  <div>
    <v-container class="grey lighten-5">
      <v-row
        no-gutters
      >
        <v-col>
          <v-card
            class="pa-2 display-flex"
            outlined
            tile
          >{{ mainContent.text }}
          </v-card>
        </v-col>
        <v-col>
          <v-card
            class="pa-2 display-flex"
            outlined
            tile
          >
            <v-img src="home_page_img.jpg" max-width="620"></v-img>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  computed: {
    mainContent() {
      return this.$store.getters.allMainContent;
    },
  },
  async mounted() {
    await this.$store.dispatch('getMainContent')
  },
}
</script>
