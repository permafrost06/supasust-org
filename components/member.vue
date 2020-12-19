<template>
  <figure v-click-outside="outsideTouch" @touchstart="isHovered = !isHovered" class="member-container">
    <img
      :src="require(`../assets/images/${img}`)"
      alt=""
      height="250px"
      width="250px"
    />
    <figcaption :class="{'hovered': isHovered}">
      <div class="member-personal-info">
        <h3>{{ name }}</h3>
        <span>{{ designation }}</span>
      </div>
      <div :class="['member-about', {'member-about-hovered': isHovered}]">
        <p>{{ about }}</p>
        <div class="social-icons">
            <a v-if="flickr" :href="flickr" target="_blank">
                <font-awesome-icon
                class="fa-2x"
                style="opacity: 80%;"
                :icon="['fab', 'flickr']"
                />
            </a>
            <a v-if="insta" :href="`https://www.instagram.com/${insta}`" target="_blank">
                <font-awesome-icon
                class="fa-2x"
                style="opacity: 80%;"
                :icon="['fab', 'instagram-square']"
                />
            </a>
        </div>
      </div>
    </figcaption>
  </figure>
</template>

<script>
export default {
  name: "member",
  directives: {
    "click-outside": {
      bind: function(el, binding) {
        // Define ourClickEventHandler
        const ourClickEventHandler = event => {
          if (!el.contains(event.target) && el !== event.target) {
            // as we are attaching an click event listern to the document (below)
            // ensure the events target is outside the element or a child of it
            binding.value(event); // before binding it
          }
        };
        // attached the handler to the element so we can remove it later easily
        el.__vueClickEventHandler__ = ourClickEventHandler;

        // attaching ourClickEventHandler to a listener on the document here
        document.addEventListener("touchstart", ourClickEventHandler);
      },
      unbind: function(el) {
        // Remove Event Listener
        document.removeEventListener("touchstart", el.__vueClickEventHandler__);
      }
    }
  },
  props: {
    img: {
      type: String,
      default: "blank-profile.jpg"
    },
    name: String,
    designation: String,
    about: String,
    flickr: String,
    insta: String
  },
  data: function() {
      return {
          isHovered: false
      }
  },
  methods: {
    outsideTouch() {
      this.isHovered = false;
    }
  }
};
</script>

<style lang="scss" scoped>
  *,
  *::before,
  *::after {
    box-sizing: border-box;
    margin: 0;
  }

  .member-container {
    position: relative;
    color: white;
    font-family: "Montserrat", Sans-serif;
  }

  .member-personal-info {
    margin-bottom: 15px;
  }
  
  .member-about {
    transform: translateY(100%);
    transition: transform .4s,-webkit-transform .4s,-moz-transform .4s;
  }
  
  img {
    display: block;
    position: relative;
    margin: 0;
    border: none;
    height: auto;
    width: 100%;
    max-width: 250px;
  }

  p, span {
    font-size: .8em;
  }
  
  p {
    margin-bottom: 15px;
    padding: 0;
  }

  figcaption {
    bottom: 0;
    left: 0;
    right: 0;
    max-width: 250px;
    position: absolute;
    padding: 1rem;
    overflow: hidden;
    background-color: rgba(0, 0, 0, 0.51);
    transform: translateY(100%) translateY(-75px);
    transition: transform .4s,-webkit-transform .4s,-moz-transform .4s;
  }
  
  figure {
    max-width: 250px;
    max-height: 250px;
    overflow: hidden;
  }
  
  figure:hover .member-about {
    transform: translateY(0);
    transition: transform .4s,-webkit-transform .4s,-moz-transform .4s;
  }
  
  figure:hover figcaption {
    transform: translateY(0) translateY(0);
    transition: transform .4s,-webkit-transform .4s,-moz-transform .4s;
  }
  
  .member-about-hovered {
    transform: translateY(0);
    transition: transform .4s,-webkit-transform .4s,-moz-transform .4s;
  }
  
  .hovered {
    transform: translateY(0) translateY(0);
    transition: transform .4s,-webkit-transform .4s,-moz-transform .4s;
  }
</style>
