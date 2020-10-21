<template>
  <div>
    <section class="top-section">
      <div class="section-text">
        <h1 class="supa-font logo">
          Shahjalal University Photographers' Association
        </h1>
        <h5>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Rem illo voluptatum exercitationem nam reiciendis totam distinctio, nihil dolore atque ipsum laborum officiis! Incidunt voluptatibus itaque ex sapiente nobis. Iste, non.
        </h5>
      </div>
      <img class="section-img" src="~/assets/images/landing-top.jpg" alt="">
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
        <div class="description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum autem quia, perferendis voluptatum aperiam aliquid nostrum praesentium saepe facilis molestiae cumque, dolorum eius consectetur quas quidem atque, vero nesciunt possimus.</div>
      </div>
      <img class="section-img" src="~/assets/images/team-photo.jpg" alt="">
    </section>
    <section class="member-section">
      <h2 class="h2-underline-center">23rd Executive Committee</h2>
      <div class="member-list">
        <member/>
        <member/>
        <member/>
      </div>
      <a href="#">See all committee members</a>
    </section>
  </div>
</template>

<script>
import vfBig from '../components/vf-big';
import vfSmall from '../components/vf-small';
import member from '../components/member';
import carousel from '../components/carousel';

export default {
  components: {
    vfBig, vfSmall, member, carousel
  }
}
</script>

<style lang="scss" scoped>
section {
  display: grid;
  justify-content: space-evenly;
  grid-template-areas: "text . img";
  grid-template-columns: 2fr .25fr 1fr;
  align-content: center;
  padding: 5vh 10vw;

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

.top-section {
  padding-top: 20vh;
  padding-bottom: 0;
  // height: 100vh;

  .section-img {
    min-height: 400px;
  }
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
  grid-template-areas: "title . ." "big . small";
  grid-template-columns: 1fr .5em 1fr;
  padding: 10vh 10vw;

  .h2-underline {
    grid-area: title;
    margin: .5em;
  }

  .big {
    grid-area: big;
  }

  .small {
    grid-area: small;
    display: flex;
    flex-direction: column;
    gap: .5em;
  }
}

.member-section {
  display: grid;
  grid-template-areas: ". title ." ". members ." ". link .";
  grid-template-columns: 7vw 1fr 7vw;
  align-items: center;
  padding: 10vh 10vw;

  .h2-underline-center {
    grid-area: title;
    justify-self: center;
  }

  .member-list {
    grid-area: members;
    display: flex;
    justify-content: space-evenly;
    gap: .5em;
  }

  a {
    grid-area: link;
    justify-self: center;
    padding: 1em;
    text-decoration: underline;
  }
}
</style>
