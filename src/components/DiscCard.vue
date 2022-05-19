<template>
  <div class="my-card text-center p-3 mb-3 mx-3">
    <img :src="albumObj.poster" alt="" />
    <h2 class="p-3">{{ albumObj.title }}</h2>
    <h3>{{ albumObj.author }}</h3>
    <h3>{{ albumObj.year }}</h3>
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
