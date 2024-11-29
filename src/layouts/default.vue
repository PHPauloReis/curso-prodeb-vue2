<template>
  <v-layout>
    <v-app-bar
      color="primary"
      density="compact"
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-app-bar-title>Prodeb</v-app-bar-title>
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      :location="'bottom'"
      temporary
    >
      <v-list
        :items="items"
      />
    </v-navigation-drawer>
    <v-main>
      <router-view />
    </v-main>
  </v-layout>
</template>

<script>
  export default {
    data() {
      return {
        drawer: false,
        items: [
          {
            title: 'Foo',
            value: 'foo',
          },
          {
            title: 'Bar',
            value: 'bar',
          },
          {
            title: 'Fizz',
            value: 'fizz',
          },
          {
            title: 'Buzz',
            value: 'buzz',
          },
        ],
      }
    }
  }
</script>
