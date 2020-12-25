<template>
  <div>
    <div class="container">
      <div class="img-holder">
        <img :src="require(`../assets/images/${img}`)" alt="" />
      </div>
      <div class="description">
        <h2 class="h2-underline">{{ heading }}</h2>
        <p>
          {{ blurb }}
        </p>
        <slot></slot>
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
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.container {
  color: white;
  font-family: "Montserrat";

  background-color: rgba(0, 0, 0, 0.51);
  display: flex;
  align-items: center;

  @media (max-width: 900px) {
    display: block;
  }
}

.img-holder {
  width: 100%;
}

img {
  flex: 1;
  padding: 1em;
  width: 100%;
  min-height: 0;
}

.description {
  padding: 1em;
  padding-top: 0;
}
</style>