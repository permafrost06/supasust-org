<template>
  <div class="container">
    <div class="image"></div>
    <div class="backdrop">
      <h3>Adila Zaman</h3>
      <div>Vice-President</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'member',
  props: ['name', 'designation'],
}
</script>

<style lang="scss" scoped>
.container {
  position: relative;
  display: inline-block;
  height: 10vw;
  max-height: 250px;
}

.image {
  position:absolute;
  top:0;
  left:0;
  width:100%;
  height:100%;
  background:url("~assets/images/blank-profile.jpg");
  background-repeat:no-repeat;
  background-size:100% auto;
}

.backdrop {
  position:absolute;
  padding: 1em 1em 1.5em 1em;
  bottom:0;
  left:0;
  width:100%;
  background-color: rgba(0, 0, 0, 0.51);
}

// .backdrop {
//   position: absolute;
//   width: 250px;
//   top: 0;
//   left: 50%;
//   transform: translate(-50%, -50%);
// }
</style>