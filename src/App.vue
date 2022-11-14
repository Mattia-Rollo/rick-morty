<template>
  <div>
    <AppHeader title="rick e morty" />
    <main>
      <AppSearch />
      <CharactersList :characters="charactersList" :loading="" />
    </main>

  </div>
</template>

<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';
import AppSearch from './components/AppSearch.vue';

export default {
  components: { AppHeader, CharactersList, AppSearch },
  data() {
    return {
      apiURL: 'https://rickandmortyapi.com/api/character',
      charactersList: []
    }
  },
  methods: {
    getCharacters() {
      axios.get(this.apiURL).then(
        (res) => {
          this.charactersList = [...res.data.results]
          console.log(this.charactersList);
        })
    }
  },
  created() {
    this.getCharacters()
  }
}
</script>

<style lang="scss" scoped>
.red {
  background-color: red;

}
</style>