<template>
  <div class="my-card text-center p-3">
    <img :src="albumObj.poster" alt="" />
    <h2 class="p-3">Titolo</h2>
    <h3>Artista</h3>
    <h3>Anno</h3>
  </div>
</template>

<script>
export default {
  name: "DiscCard",
  props: {
    albumObj: Object,
  },
};
</script>

<style>
.my-card {
  background-color: #2e3a46;
}
</style>
