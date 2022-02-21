<template>
  <footer>
    <p>Copright &copy; 2022</p>
    <router-link v-show="aboutPage" to="/about">About</router-link>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  computed: {
    aboutPage() {
      return this.$route.path !== '/about';
    }
  }
}
</script>

<style scoped>
a {
  color: #333;
}
footer {
  margin-top: 30px;
  text-align: center;
}
</style>