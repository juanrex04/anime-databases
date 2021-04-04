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
          v-model="search_query"
        />
      </form>
    </header>
  </div>
</template>

<script>
export default {
}
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
</style>
