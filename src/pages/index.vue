<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <h1>Calcule o seu IMC</h1>
      </v-col>
    </v-row>
    <v-row>
      <v-col
        cols="12"
      >
        <v-text-field
          v-model="nome"
          label="Digite o seu nome"
          required
        />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <v-btn
          density="default"
          color="indigo-darken-3"
          @click="exibirDados"
        >
          Consultar
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>

import axios from 'axios';

export default {
  data() {
    return {
      peso: 0,
      altura: 0,
      nome: '',
      resposta: ''
    }
  },
  methods: {
    async exibirDados() {
      await this.obterDados()
      alert(this.resposta)
    },

    async obterDados() {
      const endpoint = `https://servicodados.ibge.gov.br/api/v2/censos/nomes/${this.nome}`

      await axios.get(endpoint)
        .then((response) => {
          this.resposta = 'Esse nome tem: ' + response.data[0].res[8].frequencia
        })
    }
  }
}

</script>
