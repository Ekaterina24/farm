<template>
  <div>
    <div>Животные</div>
    <v-btn @click="toggleForm">Форма</v-btn>
    <Form v-if="isVisible" />

    <v-card
      v-for="item in animals"
      class="mx-auto ma-6 d-flex"
      max-width="344"
    >
      <v-card-text>
        <div> {{ item.type }}</div>
        <p class="text-h4 text--primary">
          {{ item.name }}
        </p>
        <p>adjective</p>
        <div class="text--primary">
          {{ item.weight }}
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import Form from "../../components/Form";
// import axios from "axios";
export default {
  name: "index",
  components: {Form},
  data() {
    return {
      isVisible: false
    }
  },
  methods: {
    toggleForm() {
      this.isVisible = !this.isVisible
    }
  },
  computed: {
    animals() {
      return this.$store.getters.allAnimals;
    },
  },
  async mounted() {
    await this.$store.dispatch('getAnimals')
  },
}
</script>

<style scoped>

</style>
