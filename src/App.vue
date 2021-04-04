<template>
  <div class="app">
    <header>
      <h1>Anime <strong>DATABASE</strong></h1>
      <form class="searchBox" @submit.prevent="search">
        <input
          type="search"
          class="searchField"
          placeholder="Write to search"
          required
          v-model="searchQuery"
        />
      </form>
    </header>
    <main>
      <div class="cards" v-if="animelist.length > 0">
        <Card v-for="anime in animelist" :key="anime.mal_id" :anime="anime" />
      </div>

      <div class="no-result" v-else>
        Sorry anime no found...
      </div>
    </main>
  </div>
</template>

<script>
import { ref } from "vue";
import Card from "./components/card";

export default {
  components: { Card },
  setup() {
    const searchQuery = ref("");
    const animelist = ref([]);

    const search = async () => {
      animelist.value = await fetch(
        `https://api.jikan.moe/v3/search/anime?q=${searchQuery.value}`
      )
        .then((res) => res.json())
        .then((data) => data.results);

      searchQuery.value = "";
    };
    return {
      Card,
      searchQuery,
      animelist,
      search,
    };
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Oswald:wght@400;600&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Oswald", sans-serif;
}

a {
  text-decoration: none;
}

header {
  padding-top: 50px;
  padding-bottom: 50px;
  h1 {
    color: #888;
    font-size: 42px;
    font-weight: 400;
    text-align: center;
    text-transform: uppercase;
    margin-bottom: 30px;

    strong {
      color: #313131;
    }
    &:hover {
      color: #313131;
    }
  }

  .searchBox {
    display: flex;
    justify-content: center;
    padding-left: 30px;
    padding-right: 30px;

    .searchField {
      appearance: none;
      background: none;
      border: none;
      outline: none;

      background-color: #f3f3f3;
      box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.15);
      display: block;
      width: 100%;
      max-width: 600px;
      padding: 15px;
      border-radius: 8px;

      color: #313131;
      font-size: 20px;
      transition: 0.4s;

      &:focus,
      &:valid {
        color: #fff;
        background-color: #313131;
        box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.15);
      }
    }
  }
}

main {
  max-width: 1200px;
  margin: 0 auto;
  padding-left: 30px;
  padding-right: 30px;

  .cards {
    display: flex;
    flex-wrap: wrap;
    margin: 0 -8px;
  }
}
</style>
