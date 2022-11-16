<template>
<body>
  <Header title="Breaking Bad API"/>
  <Filter @filterchar="getCharacter"/>
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
          apiUrlBcs: 'https://www.breakingbadapi.com/api/characters?category=Better+Call+Saul',
          apiUrlBrb: 'https://www.breakingbadapi.com/api/characters?category=Breaking+Bad',
          characterList: [],
          loading: false,
          searchStatus: ''
      }
    },

    methods: {
      getCharacter(status){
        if (status === 'Better Call Saul') {
          axios.get(this.apiUrlBcs).then(
          (res) => {
            console.log(res.data);
            this.characterList = [...res.data];
          },
          () => {}
          )
        }
        else if (status === 'Breaking Bad') {
          axios.get(this.apiUrlBrb).then(
          (res) => {
            console.log(res.data);
            this.characterList = [...res.data];
          },
          () => {}
          )
        }
        else{
          axios.get(this.apiUrl).then(
          (res) => {
            console.log(res.data);
            this.characterList = [...res.data];
          },
          () => {}
          )
        }
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