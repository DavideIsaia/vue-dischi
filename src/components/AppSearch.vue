<template>
  <label class="p-3 text-center" for="filter-search"
    >Filtra per genere musicale
    <select
      @change="$emit('searchSelected', searchText)"
      v-model="searchText"
      class="ms-4"
      name="filter-search"
      id="filter-search"
    >
      <option value="" selected>Tutti</option>
      <option
        v-for="(genre, index) in genres"
        :key="`genre-${index}`"
        :value="genre"
      >
        {{ genre }}
      </option>
    </select>
  </label>
</template>

<script>
export default {
  name: "AppSearch",
  props: {
    genres: Array,
  },
  data() {
    return {
      searchText: "",
    };
  },
};
</script>

<style lang="scss" scoped></style>
