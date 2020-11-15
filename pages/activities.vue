<template>
  <div class="container">
    <h1>Our Activities</h1>
    <div v-for="activity in activities" v-bind:key="activity.id">
      <imageLeftTile v-if="activity.id % 2 != 0" v-bind="activity" />
      <imageRightTile v-if="activity.id % 2 == 0" v-bind="activity" />
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
      activities: [
        {
          id: 1,
          img: 'activities/bpc.jpg',
          heading: 'Basic Photography Course',
          blurb:
            'A yearly basic course for all photography enthusiasts who are willing & passionate to start photography.',
        },
        {
          id: 2,
          heading: 'Advance Photography Course',
          blurb:
            'An advance course on a particular category or genre. To explore that specific category more and work with it.',
        },
        {
          id: 3,
          img: 'activities/photo-adda.jpg',
          heading: 'Photo-Adda',
          blurb:
            "A weekly discourse among photography enthusiasts. We show each other's photos and discuss about how to improve ourselves. ",
        },
        {
          id: 4,
          img: 'activities/photo-walk.JPG',
          heading: 'Photo-Walk',
          blurb:
            'We try to arrange a short tour twice a month with photography enthusiasts. The main goal is to improve our photography skills on field.',
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