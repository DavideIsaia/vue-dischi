<template>
  <label class="p-3 text-center" for="filter-search-2"
    >Filtra per artista
    <select
      @change="$emit('searchArtist', artistSearch)"
      v-model="artistSearch"
      class="ms-4"
      name="filter-search-2"
      id="filter-search-2"
    >
      <option value="" selected>Tutti</option>
      <option
        v-for="(author, index) in authors"
        :key="`author-${index}`"
        :value="author"
      >
        {{ author }}
      </option>
    </select>
  </label>
</template>

<script>
export default {
  name: "AppSearchArtist",
  props: {
    authors: Array,
  },
  data: function () {
    return {
      artistSearch: "",
    };
  },
};
</script>

<style lang="scss" scoped></style>
