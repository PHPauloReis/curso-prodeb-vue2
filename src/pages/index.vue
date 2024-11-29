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
          v-model="peso"
          label="Digite o seu peso"
          required
        />
      </v-col>
    </v-row>
    <v-row>
      <v-col
        cols="12"
      >
        <v-text-field
          v-model="altura"
          label="Digite a sua altura"
          required
        />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <v-btn
          density="default"
          color="indigo-darken-3"
        >
          Calcular
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>

export default {
  data() {
    return {
      peso: 0,
      altura: 0
    }
  }
}

</script>
