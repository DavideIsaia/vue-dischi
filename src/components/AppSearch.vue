<template>
  <label class="p-3 text-center" for="filter-search"
    >Filtra per genere musicale
    <select
      @change="$emit('searchSelected')"
      v-model="searchText"
      class="ms-4"
      name="filter-search"
      id="filter-search"
    >
      <option value="All" selected>Tutti</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>
  </label>
</template>

<script>
export default {
  name: "AppSearch",
  data() {
    return {
      searchText: "All",
    };
  },
};
</script>

<style lang="scss" scoped>
label {
  color: white;

  select {
    min-width: 6rem;
  }
}
</style>
