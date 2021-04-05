<template>
  <div class="card">
    <a :href="anime.url" target="_BLANK">
      <img :src="anime.image_url" :alt="anime.title + 'Poster'" />
      <h2>{{ anime.title }}</h2>
    </a>
  </div>
</template>

<script>
export default {
  props: ["anime"],
};
</script>

<style scoped lang="scss">
.card {
  flex: 1 1 33%;
  width: 100%;
  max-width: 33%;
  padding: 0px 8px;
  margin-bottom: 16px;

  img {
    width: 100%;
    background-size: cover;
    overflow: hidden;
    border-radius: 16px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.15);
    transition: 0.4s;
  }

  h2 {
    padding: 16px;
    color: #ffff;
    transition: 0.4s;

    @media (max-width: 768px) {
      font-size: 15px;
    }
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
