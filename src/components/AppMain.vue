<template>
  <main class="container">
    <div class="row d-flex flex-wrap">
      <div class="col-2 mt-5">
        <DiscCard />
      </div>
    </div>
  </main>
</template>

<script>
import DiscCard from "./DiscCard.vue";

export default {
  name: "AppMain",
  components: {
    DiscCard,
  },
};
</script>

<style lang="scss" scoped></style>
