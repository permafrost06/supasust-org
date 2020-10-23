<template>
  <div>
    <div class="container">
      <div class="description">
        <font-awesome-icon
          class="fa-3x"
          style="opacity: 50%; padding: 10px"
          :icon="['fas', 'quote-left']"
        />
        {{ quote }}
        <font-awesome-icon
          class="fa-3x"
          style="position: absolute; opacity: 50%; padding: 10px"
          :icon="['fas', 'quote-right']"
        />
        <div class="author">
          <h3>{{ author }}</h3>
          {{ designation }}
        </div>
      </div>
      <img :src="require(`../assets/images/${img}`)" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'quoteImageRight',
  props: {
    img: {
      type: String,
      default: 'blank-profile.jpg',
    },
    quote: String,
    author: String,
    designation: String,
  },
}
</script>

<style lang="scss" scoped>
.container {
  background-color: rgba(0, 0, 0, 0.51);
  display: flex;
  align-items: center;
  position: relative;

  @media (max-width: 800px) {
    flex-direction: column-reverse;

    .description {
      padding: 1em 2em;
    }
  }
}

img {
  width: 50vw;
  min-width: 30vw;
  object-fit: cover;
  padding: 1.5em;
}

.description {
  padding: 0 0 0 2.5em;

  .author {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    padding: 2em;
    padding-bottom: 0;
  }
}
</style>