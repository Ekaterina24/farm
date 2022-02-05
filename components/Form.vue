<template>
  <div class="col-md-4">
    <form @submit.prevent="addAnimalToList">
      <v-text-field label="Тип" v-model="type"></v-text-field>
      <v-text-field label="Имя" v-model="name"></v-text-field>
      <v-text-field label="Вес" v-model="weight"></v-text-field>
      <v-text-field label="Цвет" v-model="color"></v-text-field>
      <v-text-field label="Пол" v-model="sex"></v-text-field>
      <v-btn type="submit">Добавить</v-btn>
    </form>
  </div>
</template>

<script>
import {mapMutations} from 'vuex'
export default {
  name: "Form",
  data() {
    return {
      type: '',
      name: '',
      weight: '',
      color: '',
      sex: ''
    }
  },
  methods: {
    ...mapMutations(['createAnimal']),
    addAnimalToList() {
      this.createAnimal({
        type: this.type,
        name: this.name,
        weight: this.weight,
        color: this.color,
        sex: this.sex
      })
      this.type = ''
      this.name = ''
      this.weight = ''
      this.color = ''
      this.sex = ''
    }
  }

}
</script>

<style scoped>

</style>
