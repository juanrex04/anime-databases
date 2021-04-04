<template>
  <div class="card">
    <a href="#" target="_BLANK">
      <img src="https://place-hold.it/150x250" alt="Anime poster" />
      <h2>Naruto</h2>
    </a>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.card {
  flex: 1 1 33%;
  width: 33%;
  max-width: 33%;
  padding: 0px 8px;
  margin-bottom: 16px;

  img {
    width: 100%;
    height: 300px;
    object-fit: cover;
    border-radius: 16px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.15);
    transition: 0.4s;
  }

  h2 {
    padding: 16px;
    color: #313131;
    transition: 0.4s;
  }

  &:hover {
    img {
      transform: scale(1.05);
    }
    h2 {
      color: #4e0b9b;
    }
  }
}
</style>
