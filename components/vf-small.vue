<template>
    <div>
        <a :href="link">
            <div class="container">
                <img v-if="img" :src="require(`../assets/images/${img}`)" alt="">
                <h4>{{ caption }}</h4>
            </div>
        </a>
    </div>
</template>

<script>
export default {
    name: 'vfSmall',
    props: {
    img: {
      type: String,
    },
    caption: {
      type: String,
      default:
        'Headline: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt.',
    },
    link: {
        type: String
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
    background-color: rgba(0, 0, 0, 0.51);
    display: flex;
    align-items: center;
    min-height: 20vh;
}

img {
    height: 20vh;
    padding: .75em;

    @media (max-width: 1300px) {
        height: 20vw;
    }
}

h4 {
    padding: 0 1.5em 0 .5em;
}
</style>