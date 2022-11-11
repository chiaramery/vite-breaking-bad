<script>
// IMPORT
// Modules
import axios from "axios";
// Components
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppSelect from './components/AppSelect.vue';
import BackLoader from "./components/BackLoader.vue";
import { store } from "./store";
// EXPORT
export default {
  components: {
    AppHeader,
    AppSelect,
    AppMain,
    BackLoader,
  },
  data() {
    return {
      store
    }
  },
  created() {
    this.store.loading = true;
    axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.characters = resp.data;
      console.log(this.store.characters);
      this.store.loading = false;
    });

    this.getCategory();
  },
  methods: {
    getCategory() {
      this.store.loading = true;
      let apiUrl = "https://www.breakingbadapi.com/api/characters";

      const urlParams = {}
      if (this.store.searchCategory) {
        urlParams.category = this.store.searchCategory;
      }

      axios.get(apiUrl, {
        params: urlParams,
      }).then((resp) => {
        this.store.characters = resp.data;
        this.store.loading = false;
      })
    }
  }
}
</script>

<template>
  <AppHeader />
  <div class="wrapper">
    <AppSelect @selectCategory="getCategory" />
    <BackLoader v-if="store.loading" />
    <AppMain v-else />

  </div>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>