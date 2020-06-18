<template>
  <div id="app">
    <b-navbar type="dark" variant="dark">
      <b-navbar-nav>
        <b-nav-item href="#">Inicio</b-nav-item>

        <!-- Navbar dropdowns -->
        <b-nav-item-dropdown text="Idioma" right>
          <b-dropdown-item href="#">EN</b-dropdown-item>
          <b-dropdown-item href="#">ES</b-dropdown-item>
          <b-dropdown-item href="#">RU</b-dropdown-item>
          <b-dropdown-item href="#">FA</b-dropdown-item>
        </b-nav-item-dropdown>

        <b-nav-item-dropdown text="Usuario" right>
          <b-dropdown-item href="#">Account</b-dropdown-item>
          <b-dropdown-item href="#">Settings</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-navbar>
    <b-container>
      <b-row class="mt-5">
        <b-col cols="4" v-for="(personaje, index) in personajes" :key="index">
          <b-card
            :title="personaje.nombre"
            :img-src="personaje.imagen"
            img-alt="Imagen"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-5"
          >
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import { mapState } from "vuex";

export default {
  name: "App",
  computed: {
    ...mapState(["personajes"]),
  },
};
</script>
