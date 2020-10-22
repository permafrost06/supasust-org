<template>
  <div class="container">
    <section class="top-section">
      <div class="section-text">
        <h1 class="supa-font logo">
          Shahjalal University Photographers' Association
        </h1>
        <h5>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Rem illo
          voluptatum exercitationem nam reiciendis totam distinctio, nihil
          dolore atque ipsum laborum officiis! Incidunt voluptatibus itaque ex
          sapiente nobis. Iste, non.
        </h5>
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
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum autem
          quia, perferendis voluptatum aperiam aliquid nostrum praesentium saepe
          facilis molestiae cumque, dolorum eius consectetur quas quidem atque,
          vero nesciunt possimus.
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
      <a href="#">See all committee members</a>
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
  padding: 10vw;
}

section {
  display: grid;
  justify-content: space-evenly;
  grid-template-areas: 'text . img';
  grid-template-columns: 2fr 0.25fr 1fr;
  align-content: center;
  padding-bottom: 10vh;

  .section-text {
    grid-area: text;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .section-img {
    grid-area: img;
    height: 30vw;
    min-height: 300px;
  }
}

.section-img {
  min-height: 400px;
}

.logo {
  font-size: 3em;
  font-weight: 100;
}

// .carousel-container {
//   display: grid;
//   grid-template-areas: ". carousel .";

//   .carousel {
//     grid-area: carousel;
//   }
// }

.vfpanel {
  display: grid;
  grid-template-areas: 'title . .' 'big . small';
  grid-template-columns: 1fr 0.5em 1fr;
  padding-bottom: 10vh;

  .h2-underline {
    grid-area: title;
    margin: 0.5em;
  }

  .big {
    grid-area: big;
  }

  .small {
    grid-area: small;
    display: flex;
    flex-direction: column;
    gap: 0.5em;
  }
}

.member-section {
  display: flex;
  flex-direction: column;
  align-items: center;

  .member-list {
    display: grid;
    justify-content: space-evenly;
    gap: 0.5em;
    grid-template-columns: repeat(3, 1fr);
    padding-bottom: 1em;
  }
}
</style>
