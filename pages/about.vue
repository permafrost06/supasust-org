<template>
  <div class="container">
    <section class="full-width">
      <img src="~/assets/images/about-supa.jpg" alt="" />
      <p>
        Shahjalal University Photographers' Association (SUPA) is the Shahjalal University of Science & Technology based photography organization estimated in 1996. "Photography for Mankind with Artistry" with this motto SUPA have been working since then for photography & photography enthusiasts.
      </p>
    </section>
    <section class="tiles normal-width">
      <imageLeftTile img="events/hiraeth.jpg" heading="Events" blurb='We arrange intra-campus, national and international exhibitions. Organize basic & advance photography courses. As an art based organization we also collab with visual artists & share experiences. We also have our own photography magazine "Viewfinder".'> <nuxt-link to="/events"><button>See all events <font-awesome-icon :icon="['fas', 'chevron-right']" /></button></nuxt-link> </imageLeftTile>
      <imageRightTile img="activities/photo-walk.JPG" heading="Activities" blurb="We have weekly and monthly activities for photography enthusiasts and practitioners. We also try to arrange and join in different social welfare activities."> <nuxt-link to="/activities"><button>See all activities <font-awesome-icon :icon="['fas', 'chevron-right']" /></button></nuxt-link> </imageRightTile>
      <imageLeftTile img="advisors.jpg" heading="Advisors" blurb="SUPA wouldn't be where it stands today if it was not for the support of our beloved advisors."> <nuxt-link to="/advisors"><button>Meet our advisors <font-awesome-icon :icon="['fas', 'chevron-right']" /></button></nuxt-link> </imageLeftTile>
      <imageRightTile img="team-photo.jpg" heading="Executive Committee" blurb="Meet the minds behind Shahjalal University Photographers' Association."> <nuxt-link to="/team"><button>See executive committee <font-awesome-icon :icon="['fas', 'chevron-right']" /></button></nuxt-link> </imageRightTile>
    </section>
    <section class="timeline-section">
      <h2 class="h2-underline-center"><span class="supa-font">SUPA</span> Timeline</h2>
      <timeline />
    </section>
  </div>
</template>

<script>
import imageLeftTile from '../components/imageLeftTile'
import imageRightTile from '../components/imageRightTile'
import timeline from '../components/timeline'

export default {
  components: {
    imageLeftTile,
    imageRightTile,
    timeline
  },
}
</script>

<style lang="scss" scoped>
.container {
  padding-top: 10vw;

  @media (max-width: 850px) {
    padding-top: 10vh;
  }
}

.full-width {
  overflow: hidden;

  img {
    width: 100vw;
    height: 80vh;
    object-fit: cover;
  }

  p {
    position: absolute;
    bottom: 1em;
    right: 5vw;
    text-align: right;
    background-color: rgba(0, 0, 0, 0.4);
    color: white;
    font-weight: 800;
    font-size: 1.25em;
    width: 45vw;
    padding: 1em;
  }

  .supa-font {
    font-family: "Bauhaus 93";
    font-size: 1.25em;
    line-heighT: 1em;
    font-weight: 500;
  }

  @media (max-width: 850px) {
    p {
      font-size: 1em;
      width: 80vw;
      bottom: 5em;
    }
  }
}

.normal-width {
  margin: 0 10vw;
}

.tiles > div {
  margin-bottom: 1em;

  button {
    font-family: "Montserrat";
    background: transparent;
    color: white;
    border: 2px solid #fff;
    border-radius: 8px;
    padding: .5em 1em;
    font-size: 1em;
    font-weight: 500;
    cursor: pointer;
  }
}

.supa-font {
  font-size: 1.5em;
}

section {
    padding-bottom: 10vh;
}

.timeline-section {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>