<template>
  <div class="container">
    <h1>Our Activities</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Et provident
      repudiandae inventore perferendis impedit sunt aliquam quisquam quas! Hic
      quaerat magni earum vel. Est soluta voluptatum molestiae eveniet, sequi
      aspernatur. Lorem ipsum dolor, sit amet consectetur adipisicing elit.
      Odit, necessitatibus placeat ex vitae suscipit aliquid eius natus
      veritatis sunt, facilis ea repellat explicabo beatae, unde quaerat
      architecto. Odio, nostrum laborum.
    </p>
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
          img: 'vf-photo-1.jpg',
          heading: 'Headline 1',
          blurb:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat id fugit, reprehenderit aperiam earum dolorum facilis modi tempora doloremque, commodi molestiae eligendi. Commodi esse eius impedit id distinctio incidunt ipsum.',
        },
        {
          id: 2,
          img: 'vf-photo-2.jpg',
          heading: 'Headline 2',
          blurb:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat id fugit, reprehenderit aperiam earum dolorum facilis modi tempora doloremque, commodi molestiae eligendi. Commodi esse eius impedit id distinctio incidunt ipsum.',
        },
        {
          id: 3,
          img: 'vf-photo-3.jpg',
          heading: 'Headline 3',
          blurb:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat id fugit, reprehenderit aperiam earum dolorum facilis modi tempora doloremque, commodi molestiae eligendi. Commodi esse eius impedit id distinctio incidunt ipsum.',
        },
        {
          id: 4,
          img: 'vf-photo-4.jpg',
          heading: 'Headline 4',
          blurb:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat id fugit, reprehenderit aperiam earum dolorum facilis modi tempora doloremque, commodi molestiae eligendi. Commodi esse eius impedit id distinctio incidunt ipsum.',
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