<template>
  <header>
    <a href="https://www.spotify.com/">
      <img src="../assets/spotify-download-logo-30.png" alt="Spotify logo" />
    </a>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
};
</script>

<style lang="scss" scoped>
header {
  background-color: #2e3a46;

  img {
    width: 80px;
    margin: 0.5rem 2rem;
  }
}
</style>
