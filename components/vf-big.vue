<template>
  <div class="vfbig-container">
    <a href="#">
      <div class="content">
        <h4>
          Headline: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed
          do eiusmod tempor incididunt.
        </h4>
        <img src="~/assets/images/vf-photo-2.jpg" alt="" />
      </div>
    </a>
  </div>
</template>

<script>
export default {
  name: 'vfBig',
  props: {
    img: {
      type: String,
      default: 'blank-profile.jpg',
    },
    caption: {
      type: String,
      default:
        'Headline: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt.',
    },
  },
}
</script>

<style lang="scss" scoped>
.vfbig-container {
  display: flex;
  background: rgba(0, 0, 0, 0.51);
  padding: 1em;
  align-items: center;
  justify-content: center;

  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 1em;
    
    h4 {
      text-align: center;
      max-width: 500px;
    }

    img {
      max-height: 350px;
      height: 50vw;
      padding: 0.75em;
    }
  }
}
</style>