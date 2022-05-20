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
      <option value="Bon Jovi">Bon Jovi</option>
      <option value="Queen">Queen</option>
      <option value="Sting">Sting</option>
      <option value="Steve Gadd Band">Steve Gadd Band</option>
      <option value="Iron Maiden">Iron Maiden</option>
      <option value="Eric Clapton">Eric Clapton</option>
      <option value="Deep Purple">Deep Purple</option>
      <option value="Metallica">Metallica</option>
      <option value="Dave Weckl">Dave Weckl</option>
      <option value="Michael Jackson">Michael Jackson</option>
    </select>
  </label>
</template>

<script>
export default {
  name: "AppSearchArtist",
  data: function () {
    return {
      artistSearch: "",
    };
  },
};
</script>

<style lang="scss" scoped></style>
