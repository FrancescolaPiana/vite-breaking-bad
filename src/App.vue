<template>
<body>
  <Header/>
  <Filter/>
  <main>
    <Main/>
  </main>
</body>
</template>

<script>
import Header from './components/Header.vue';
import Filter from './components/Filter.vue';
import Main from './components/Main.vue';

  export default {
    components: {
      Header,
      Filter,
      Main,
    }
  }
</script>

<style lang="scss" scoped>
  body{
    background-color: #151515;
    height: 100vh;
  }
</style>