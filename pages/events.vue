<template>
  <div class="container">
    <h1>Events</h1>
    <div v-for="event in events" v-bind:key="event.id">
      <imageLeftTile v-if="event.id % 2 != 0" v-bind="event" />
      <imageRightTile v-if="event.id % 2 == 0" v-bind="event" />
    </div>
  </div>
</template>

<script>
import imageLeftTile from '../components/imageLeftTile'
import imageRightTile from '../components/imageRightTile'

export default {
  components: {
    imageLeftTile,
    imageRightTile,
  },
  data() {
    return {
      events: [
        {
          id: 1,
          img: 'events/visual-festival.jpg',
          heading: 'Visual Festival',
          blurb:
            "We arrange this program to bring different types of visual art practitioners together and share each others' views.",
        },
        {
          id: 2,
          img: 'events/hiraeth.jpg',
          heading: 'Hiraeth',
          blurb:
            'An intra SUST photography exhibition to promote and encourage the photography enthusiasts of our campus.',
        },
        {
          id: 3,
          img: 'events/inquest-insight.jpg',
          heading: 'Inquest Insight',
          blurb:
            "An international Photography exhibition, mainly signifying the theme 'Inquest Insight'; which depicts the fragrance of inner-self.",
        },
        {
          id: 4,
          heading: 'Viewfinder',
          blurb:
            "Photography magazine containing articles, portfolios, biographies and many more photography related materials.",
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  padding: 10vw;

  @media (max-width: 850px) {
    padding: 10vh 10vw;
  }

  & > div {
    padding: 2em 0;
  }
}
</style>