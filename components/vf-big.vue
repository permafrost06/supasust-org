<template>
  <div class="container">
    <div class="image"></div>
    <div class="backdrop">
      <h3>
        Headline: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed
        do eiusmod tempor incididunt.
      </h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'vfBig',
  props: ['img', 'caption'],
}
</script>

<style lang="scss" scoped>
.container {
  position: relative;
  display: inline-block;
}

.image {
  position:absolute;
  top:0;
  left:0;
  width:100%;
  height:100%;
  background:url('~assets/images/vf-photo-1.jpg');
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.backdrop {
  position:absolute;
  padding: 1em 1em 1.5em 1em;
  bottom:0;
  left:0;
  width:100%;
  background-color: rgba(0, 0, 0, 0.51);
}
</style>