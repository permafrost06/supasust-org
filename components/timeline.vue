<template>
  <div class="timeline-container">
    <ul class="timeline" ref="timeline">
      <li v-for="milestone in milestones" :key="milestone.date">
        <div class="blank"><div class="marker"></div></div>
        <div class="content">
          <div class="line"></div>
          <div class="text">
            <h3>{{ milestone.date }}</h3>
            <p>{{ milestone.text }}</p>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import { gsap } from "gsap";
import ScrollTrigger from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
  name: "timeline",
  components: {
    ScrollTrigger,
  },
  data() {
    return {
      milestones: [
        {
          date: "06 June, 1996",
          text: "SUPA Established",
        },
        {
          date: "21-23 November, 1996",
          text: "First Workshop on Basic Photography",
        },
        {
          date: "02 December, 1998",
          text: "First workshop Tour at Jaflong",
        },
        {
          date: "01 January, 1999",
          text: "First Calendar Published",
        },
        {
          date: "26-30 September, 1999",
          text: "First Exhibition",
        },
        {
          date: "16 October, 2000",
          text: "First T-Shirt lanuch",
        },
        {
          date: "April 2001",
          text: "First International Tour at Shilong (Meghaloya, India)",
        },
        {
          date: "July, 2001",
          text: "First Out of Campus Exhibition at Shahid Soleman Hall, Sylhet",
        },
        {
          date: "July 2001",
          text: "First Edition of “Viewfinder” published",
        },
        {
          date: "January, 2003",
          text: "First Workshop on Advanced Photography",
        },
        {
          date: "12-14 February, 2016",
          text: "First National Exhibition",
        },
        {
          date: "21-23 April, 2017",
          text: "First Exhibition at Shilpakala Academy, Dhaka",
        },
        {
          date: "12-14 November, 2017",
          text: "First Intra-SUST Photography Exhibition",
        },
        {
          date: "February-March, 2018",
          text: "First International Exhibition",
        },
        {
          date: "12-13 March, 2020",
          text:
            "First Exhibition at an International Venue at Gallery Gold, Kolkata, India",
        },
        {
          date: "April-May, 2020",
          text: "Charity Photo Sale - Artistry for Entity",
        },
        {
          date: "17-24 July, 2020",
          text: "First Virtual Exhibition",
        },
      ],
    };
  },
  mounted: function () {
    var tl = gsap.timeline({
      scrollTrigger: { trigger: ".timeline" },
      defaults: { duration: 1 },
    });

    var numEl = this.$refs.timeline.children.length;

    tl.from(".marker", { scale: 0, ease: "elastic.out(1, 0.3)", stagger: 0.3 })
      .from(
        ".line",
        { width: 0, ease: "expo.out", stagger: 0.3 },
        "-=" + numEl * 0.32
      )
      .from(
        ".text",
        { opacity: 0, y: -30, ease: "power2.out", stagger: 0.3 },
        "-=" + numEl * 0.32
      );
  },
};
</script>

<style lang="scss">
@media (max-width: 680px) {
  .timeline-container {
    display: flex;
    justify-content: center;
  }
}

.timeline {
  list-style: none;
  padding: 0;
  margin: 0;

  * {
    box-sizing: content-box;
  }

  li {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-areas: "left right";

    .marker {
      content: "";
      height: 10px;
      width: 10px;
      background-color: #222;
      border-radius: 50%;
      border: 2px solid white;
      margin-right: -8px;
      z-index: 999;
    }

    .content {
      padding: 1em;

      .line {
        grid-area: line;
        content: "";
        height: 2px;
        width: 60px;
        background-color: white;
      }

      h3 {
        margin: 0;
      }

      p {
        padding: 0;
        margin: 0;
        font-size: 0.9em;
      }
    }
  }

  li:nth-child(odd) {
    @media (max-width: 680px) {
      grid-template-columns: 1em 1fr;
    }

    .blank {
      grid-area: left;
      border-right: 1px solid white;
      display: flex;
      justify-content: flex-end;
      align-items: center;

      .marker {
        margin-right: -8px;
      }
    }

    .content {
      grid-area: right;
      border-left: 1px solid white;
      padding-left: 0;
      display: grid;
      grid-template-areas: "line text";
      grid-template-columns: 70px 1fr;
      align-items: center;

      .text {
        grid-area: text;
        text-align: left;
      }
    }
  }

  li:nth-child(even) {
    grid-template-areas: "left right";

    @media (max-width: 680px) {
      grid-template-columns: 1em 1fr;
    }

    .blank {
      grid-area: right;
      border-left: 1px solid white;
      display: flex;
      justify-content: flex-start;
      align-items: center;

      @media (max-width: 680px) {
        grid-area: left;
        border-left: none;
        border-right: 1px solid white;
        justify-content: flex-end;
      }

      .marker {
        margin-left: -8px;

        @media (max-width: 680px) {
          margin-left: 0;
          margin-right: -8px;
        }
      }
    }

    .content {
      grid-area: left;
      border-right: 1px solid white;
      padding-right: 0;
      display: grid;
      grid-template-areas: "text line";
      grid-template-columns: 1fr 70px;
      align-items: center;
      justify-items: end;

      @media (max-width: 680px) {
        grid-area: right;
        border-right: none;
        border-left: 1px solid white;
        padding-right: 1em;
        padding-left: 0;
        grid-template-areas: "line text";
        grid-template-columns: 70px 1fr;
        justify-items: start;
      }

      .text {
        grid-area: text;
        text-align: right;

        @media (max-width: 680px) {
          text-align: left;
        }
      }
    }
  }
}
</style>