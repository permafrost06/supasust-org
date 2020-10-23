<template>
  <div class="container">
    <section class="top-section">
      <div class="section-text">
        <h1 class="supa-font logo">
          Shahjalal University<br />
          Photographers' Association
        </h1>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Rem illo
          voluptatum exercitationem nam reiciendis totam distinctio, nihil
          dolore atque ipsum laborum officiis! Incidunt voluptatibus itaque ex
          sapiente nobis. Iste, non.
        </p>
      </div>
      <img class="section-img" src="~/assets/images/landing-top.jpg" alt="" />
    </section>
    <!-- <div class="carousel-container">
      <carousel class="carousel"/>
    </div> -->
    <div class="vfpanel">
      <h2 class="h2-underline">Viewfinder Articles</h2>
      <vfBig class="big" />
      <div class="small">
        <vfSmall />
        <vfSmall />
        <vfSmall />
      </div>
    </div>
    <section class="team">
      <div class="section-text">
        <h2 class="h2-underline">Our Team</h2>
        <div class="description">
          <p class="no-padding">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum autem
            quia, perferendis voluptatum aperiam aliquid nostrum praesentium
            saepe facilis molestiae cumque, dolorum eius consectetur quas quidem
            atque, vero nesciunt possimus.
          </p>
        </div>
      </div>
      <img class="section-img" src="~/assets/images/team-photo.jpg" alt="" />
    </section>
    <div class="member-section">
      <h2 class="h2-underline-center">Executive Committee</h2>
      <div class="member-list">
        <div v-for="member in members" v-bind:key="member.id">
          <member v-bind="member" />
        </div>
      </div>
      <nuxt-link to="/team" class="nuxt_link"
        >See all committee members</nuxt-link
      >
    </div>
  </div>
</template>

<script>
import vfBig from '../components/vf-big'
import vfSmall from '../components/vf-small'
import member from '../components/member'
import carousel from '../components/carousel'

export default {
  components: {
    vfBig,
    vfSmall,
    member,
    carousel,
  },
  data() {
    return {
      members: [
        {
          id: 1,
          img: 'members/Shohan Ur Rahaman.jpg',
          name: 'Shohan Ur Rahman',
          designation: 'President',
        },
        {
          id: 5,
          img: 'members/Prem Raj Saha.jpg',
          name: 'Prem Raj Saha',
          designation: 'General Secretary',
        },
        {
          id: 7,
          img: 'members/Radia Islam.jpg',
          name: 'Radia Islam',
          designation: 'Chief Instructor',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  padding: 10vh 10vw;
}

section {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 5vh 0;

  h1 {
    padding: 0;
  }

  .section-img {
    max-height: 40vh;
    max-width: 80vw;
  }
}

.vfpanel {
  display: flex;
  flex-direction: column;
  gap: 0.5em;

  .small {
    display: flex;
    flex-direction: column;
    gap: 0.5em;
  }
}

.member-section {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 0 3em;

    .member-list {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1em;
        padding-bottom: 1em;
    }

    .nuxt_link {
        font-size: .75em;
        text-align: center;
    }
}
</style>
