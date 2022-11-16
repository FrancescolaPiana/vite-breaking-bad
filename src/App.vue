<template>
<body>
  <Header title="Breaking Bad API"/>
  <Filter/>
  <main>
    <Main :characters="characterList"/>
  </main>
</body>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Filter from './components/Filter.vue';
import Main from './components/Main.vue';

  export default {
    components: {
      Header,
      Filter,
      Main,
    },

    data() {
      return {
          apiUrl: 'https://www.breakingbadapi.com/api/characters',
          characterList: [],
          loading: false,
          searchStatus: ''
      }
    },

    methods: {
      getCharacter(){
        axios.get(this.apiUrl).then(
          (res) => {
            console.log(res.data);
            this.characterList = [...res.data];
          },
          () => {}
          )
      }
    },

    created() {
      this.getCharacter()
    },
  }
</script>

<style lang="scss" scoped>
  body{
    background-color: #151515;
    height: 100%;
  }
</style>