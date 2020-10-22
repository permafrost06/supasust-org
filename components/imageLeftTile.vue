<template>
  <div>
    <div class="container">
      <img :src="require(`../assets/images/${img}`)" alt="" />
      <div class="description">
        <h2 class="h2-underline">{{ heading }}</h2>
        <p>
          {{ blurb }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'imageLeftTile',
  props: {
    img: {
      type: String,
      default: 'blank-profile.jpg',
    },
    heading: String,
    blurb: String,
  }
}
</script>

<style lang="scss" scoped>
.container {
  background-color: rgba(0, 0, 0, 0.51);
  display: flex;
  align-items: center;
}

img {
  width: 50vw;
  min-width: 30vw;
  object-fit: cover;
  padding: 1.5em;
}

.description {
  padding: 0 1.5em 0 0.5em;
}

h2 {
  margin: 5px;
}
</style>