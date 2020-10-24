<template>
  <div class="member-container">
    <img :src="require(`../assets/images/${img}`)" alt="" />
    <figcaption class="backdrop">
      <h3>{{ name }}</h3>
      <div>{{ designation }}</div>
    </figcaption>
  </div>
</template>

<script>
export default {
  name: 'member',
  props: {
    img: {
      type: String,
      default: 'blank-profile.jpg',
    },
    name: String,
    designation: String,
  },
}
</script>

<style lang="scss" scoped>
.member-container {
  position: relative;
}

img {
  width: 100%;
  display: block;
  position: relative;
  margin: 0;
  border: none;
  max-width: 100%;
  height: auto;
}

figcaption {
  bottom: 0;
  left: 0;
  right: 0;
  position: absolute;
  padding: 20px;
  overflow: hidden;
  background-color: rgba(0, 0, 0, 0.51);
  
  @media (max-width: 750px) {
    font-size: .4em;
    padding: 5px;
  }
}
</style>