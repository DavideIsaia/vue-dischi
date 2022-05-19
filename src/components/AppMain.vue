<template>
  <main class="container">
    <div class="row row-cols-6 mt-5">
      <DiscCard
        v-for="(element, index) in albums"
        :key="index"
        :albumObj="element"
      />
    </div>
  </main>
</template>

<script>
import DiscCard from "./DiscCard.vue";
import axios from "axios";

export default {
  name: "AppMain",
  components: {
    DiscCard,
  },
  data: function () {
    return {
      albums: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.albums = resp.data.response;
      });
  },
};
</script>

<style lang="scss" scoped></style>
