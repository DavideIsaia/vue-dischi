<template>
  <main>
    <div v-if="success" class="container">
      <div class="row row-cols-1">
        <AppSearch @searchSelected="optionSelected($event)" />
        <AppSearchArtist @searchArtist="artistSelected($event)" />
      </div>
      <div class="row row-cols-3 row-cols-lg-6 mt-4">
        <DiscCard
          v-for="(element, index) in albumsFiltered"
          :key="index"
          :albumObj="element"
        />
      </div>
    </div>
    <div v-else class="container">
      <div class="my-loader text-center"><AppLoading /></div>
    </div>
  </main>
</template>

<script>
import DiscCard from "./DiscCard.vue";
import AppLoading from "./AppLoading";
import AppSearch from "./AppSearch.vue";
import AppSearchArtist from "./AppSearchArtist.vue";
import axios from "axios";

export default {
  name: "AppMain",
  components: {
    DiscCard,
    AppLoading,
    AppSearch,
    AppSearchArtist,
  },
  data: function () {
    return {
      albums: [],
      success: false,
      genre: "",
      author: "",
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.albums = resp.data.response;
        this.success = resp.data.success;
      });
  },
  computed: {
    albumsFiltered() {
      const filteredArray = this.albums.filter((element) => {
        return (
          element.genre.includes(this.genre) &&
          element.author.includes(this.author)
        );
      });
      return filteredArray;
    },
  },
  methods: {
    optionSelected(event) {
      this.genre = event;
    },
    artistSelected(event) {
      this.author = event;
    },
  },
};
</script>

<style lang="scss" scoped>
.my-loader {
  position: absolute;
  top: 50%;
  right: 50%;
  transform: translate(50%, -50%);
}
</style>
