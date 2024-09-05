<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer">
      <Menu @logout="deslogar" titulo="Menu Principal" />
    </v-navigation-drawer>
    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-app-bar-title>Application</v-app-bar-title>
      <v-spacer></v-spacer>
      <v-chip class="mr-2" :color="(logged) ? 'green' : 'error'" label> {{  status }}</v-chip>
    </v-app-bar>

    <v-main>
      <v-container>
        <RouterView />
      </v-container>
    </v-main>
  </v-app>
</template>
<script setup>
import { ref, computed } from 'vue'
import { useRoute } from 'vue-router';

const route = useRoute();

const drawer = ref(true);
const logged = ref(true);
const status = computed( () => {
  return (logged.value) ? 'Logado' : 'Deslogado';
});

const deslogar = () => {
  logged.value = false;
}


</script>
