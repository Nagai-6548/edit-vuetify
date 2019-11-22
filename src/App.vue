<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      Vuetify お試し
    </v-app-bar>
    <v-content>
      <FixedTable/>
    </v-content>
  </v-app>
</template>

<script>
import FixedTable from './components/FixedTable';

export default {
  name: 'App',

  components: {
    FixedTable,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
#app {
  height: 100%;
}
</style>
