<template>
  <div>
    <v-row>
      <v-col xs="6" sm="5" md="4">
        <v-select
          v-model="f_categoria"
          :items="categoria"
          label="Categoria"
        ></v-select>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import API from '~/services/api'
export default {
  async asyncData() {
    let categoria = [
      'Especifico de bombero',
      'Materias Jurídicas comunes',
      'Estatutos de autonomía',
      'Geografía específica',
      'Planes de emergencias'
    ]

    categoria.forEach(async x => {
      if (x === 'Especifico de bombero') {
        var select = await API.select_question(categoria)
        return console.log(select)
      }
    })
  },
  data() {
    return {
      f_categoria: '',
      categoria: [
        'Especifico de bombero',
        'Materias Jurídicas comunes',
        'Estatutos de autonomía',
        'Geografía específica',
        'Planes de emergencias',
        'N/A'
      ]
    }
  }
}
</script>

<style></style>
