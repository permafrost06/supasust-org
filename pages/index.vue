<template>
  <div class="container">
    <section class="top-section">
      <div class="section-text">
        <h1 class="supa-font logo">
          Shahjalal University Photographers' Association
        </h1>
        <p class="big-text" style="padding-right: 1em">
          Shahjalal University Photographers' Association (SUPA) is the
          photography club of Shahjalal University of Science and Technology
          (SUST), Sylhet. SUPA has been working for advancement in the field of
          photography both in SUST campus and outside since its founding in
          1996.
        </p>
      </div>
      <img class="section-img" src="~/assets/images/landing-top.jpg" alt="" />
    </section>
    <client-only>
      <div class="carousel-container">
        <splide :options="options" class="slider">
          <splide-slide>
            <div class="splide__slide__container">
              <img
                src="~/assets/images/carousel/inquest-insight-carousel.jpg"
              />
            </div>
            <a href="https://submission.supasust.org/" target="_blank">
              <div class="caption">
                <h2>Inquest Insight</h2>
                <p class="description">
                  The call for photos for our International Photography Exhibiton
                  "Inquest Insight 6: Resilience" is live now! Click here to
                  submit your photos!
                </p>
              </div>
            </a>
          </splide-slide>
          <splide-slide>
            <div class="splide__slide__container">
              <img src="~/assets/images/carousel/hiraeth-iv.jpg" />
            </div>
            <div class="caption">
              <h2>Hiraeth</h2>
              <p class="description">
                HIRAETH is an intra-SUST photography exhibition.
              </p>
            </div>
          </splide-slide>
          <splide-slide>
            <div class="splide__slide__container">
              <img src="~/assets/images/carousel/bpc-carousel.jpg" />
            </div>
            <div class="caption">
              <h2>Basic Photography Course</h2>
              <p class="description">
                Basic Photography Course (BPC) is a course run by Shahjalal
                University Photographers' Association to teach the basics of
                photography who are interested in photography. SUPA has
                successfully completed 33rd courses till now.
              </p>
            </div>
          </splide-slide>
          <template v-slot:controls>
            <div class="splide__progress">
              <div class="splide__progress__bar"></div>
            </div>
          </template>
        </splide>
      </div>
    </client-only>
    <h2 class="h2-underline">Viewfinder Articles</h2>
    <div class="vfpanel">
      <vfBig class="big" v-bind="articles[0]" />
      <div class="small">
        <vfSmall v-bind="articles[1]" />
        <vfSmall v-bind="articles[2]" />
        <vfSmall v-bind="articles[3]" />
      </div>
    </div>
    <section class="team">
      <div class="section-text">
        <h2 class="h2-underline">Our Team</h2>
        <div class="description">
          <p class="no-padding" style="padding-right: 1em">
            SUPA is led by a diverse team of university students who come from
            all corners of Bangladesh. Currently SUPA is led by the 23rd
            Executive Committee.
          </p>
        </div>
      </div>
      <div class="image-holder">
        <img
          class="section-img-landscape"
          src="~/assets/images/team-photo.jpg"
          alt=""
        />
      </div>
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
import vfBig from "../components/vf-big";
import vfSmall from "../components/vf-small";
import member from "../components/member";
import carousel from "../components/carousel";

if (process.client) {
  var Splide = require("@splidejs/vue-splide").Splide;
  var SplideSlide = require("@splidejs/vue-splide").SplideSlide;
  require("@splidejs/splide/dist/css/themes/splide-skyblue.min.css");
}

export default {
  components: {
    vfBig,
    vfSmall,
    member,
    carousel,
    Splide,
    SplideSlide,
  },
  data() {
    return {
      options: {
        type: "loop",
        gap: "1rem",
        width: "80vw",
        heightRatio: 9 / 16,
        cover: true,
        focus: "center",
        autoplay: true,
        pauseOnHover: true,
        pauseOnFocus: false,
        resetProgress: false,
        arrows: false,
        drag: true,
      },
      articles: [
        {
          id: 2,
          img: "article-2.jpg",
          caption: "Street Photography using Mobile Phone Camera",
          link:
            "https://viewfinder.supasust.org/street-photography-using-mobile-phone-camera",
        },
        {
          id: 1,
          caption: "Photography: From Passion to Profession",
          link:
            "https://viewfinder.supasust.org/photography-from-passion-to-profession",
        },
        {
          id: 3,
          img: "article-3.png",
          caption:
            "Mobile Photography: Take your photography to the next level",
          link:
            "https://viewfinder.supasust.org/mobile-photography-take-your-photography-to-the-next-level",
        },
        {
          id: 4,
          img: "article-4.jpg",
          caption: "সাদাকালো ছবি ও তৎ সম্পর্কিত অন্যান্য বিষয়াবলী",
          link:
            "https://viewfinder.supasust.org/black-and-white-photography-and-subsequent",
        },
      ],
      members: [
        {
          id: 1,
          img: "members/Shohan Ur Rahaman.jpg",
          name: "Shohan Ur Rahman",
          designation: "President",
        },
        {
          id: 5,
          img: "members/Prem Raj Saha.jpg",
          name: "Prem Raj Saha",
          designation: "General Secretary",
        },
        {
          id: 7,
          img: "members/Radia Islam.jpg",
          name: "Radia Islam",
          designation: "Chief Instructor",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.container {
  padding: 10vw;

  @media (max-width: 850px) {
    padding: 10vh 10vw;
  }
}

section {
  display: flex;
  justify-content: space-evenly;
  padding: 5vh 0;
  align-items: center;

  .big-text {
    font-size: 1.25em;
  }

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

  .section-img-landscape {
    flex: 1;
    padding: 1em;
    width: 100%;
    min-height: 0;
  }

  @media (max-width: 850px) {
    flex-direction: column;

    h1 {
      padding: 0;
    }

    .section-img {
      max-height: 40vh;
      max-width: 80vw;
    }
  }
}

.section-img {
  min-height: 400px;
}

.logo {
  font-size: 3em;
  font-weight: 100;
}

.carousel-container {
  margin: 10vh 0;

  img {
    position: relative;
  }

  .caption {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.7);
    padding: 1em;

    h2 {
      margin: 0;
      padding: 0;
    }

    p {
      margin: 0;
      padding: 0;
    }
  }

  @media (max-width: 675px) {
    img {
      position: static;
    }

    .caption {
      position: static;
      padding: 0.5em;

      p {
        font-size: 0.7em;
      }
    }
  }
}

.vfpanel {
  display: flex;
  gap: 0.5em;

  @media (max-width: 1300px) {
    flex-direction: column;
  }

  .h2-underline {
    grid-area: title;
    margin: 0.5em;
  }

  .big {
    grid-area: big;
    // height: calc(60vh + 1em);
  }

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

  .member-list {
    display: grid;
    justify-content: space-evenly;
    gap: 0.5em;
    grid-template-columns: repeat(3, 1fr);
    padding-bottom: 1em;

    @media (max-width: 750px) {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1em;
      padding: 0 1em 1em 1em;
    }

    .nuxt_link {
      font-size: 0.75em;
      text-align: center;
    }
  }
}
</style>
