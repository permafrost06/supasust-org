<template>
  <div class="gallery-container">
    <h1>Gallery</h1>
    <client-only>
      <VueJustifiedLayout :items="images" v-slot="{ item }">
        <a
          data-fancybox="gallery"
          :data-caption="item.artist"
          :href="require(`../assets/images/gallery/${item.url}`)"
        >
          <img :src="require(`../assets/images/gallery/${item.url}`)" />
          <div class="artist">{{ item.artist }}</div>
        </a>
      </VueJustifiedLayout>
    </client-only>
  </div>
</template>

<script>
import VueJustifiedLayout from "../components/justifiedGallery";

if (process.client) {
  var $ = require("jquery");
  window.jQuery = $;
  var fancybox = require("@fancyapps/fancybox");
  require("@fancyapps/fancybox/dist/jquery.fancybox.min.css");
}

export default {
  components: { VueJustifiedLayout },
  data() {
    return {
      images: [
        {
          width: 720,
          height: 1080,
          artist: "Adila Zaman",
          url: "Adila Zaman (1).jpg",
        },
        {
          width: 720,
          height: 1080,
          artist: "Adila Zaman",
          url: "Adila Zaman (2).jpg",
        },
        {
          width: 1620,
          height: 1080,
          artist: "Adila Zaman",
          url: "Adila Zaman (3).jpg",
        },
        {
          width: 1631,
          height: 1080,
          artist: "Ashraful Bari Ovi",
          url: "Ashraful Bari Ovi (1).jpg",
        },
        {
          width: 1631,
          height: 1080,
          artist: "Ashraful Bari Ovi",
          url: "Ashraful Bari Ovi (2).jpg",
        },
        {
          width: 1620,
          height: 1080,
          artist: "Ashraful Bari Ovi",
          url: "Ashraful Bari Ovi (3).jpg",
        },
        {
          width: 1440,
          height: 1080,
          artist: "Atik Ishrak Chowdhury",
          url: "Atik Ishrak Chowdhury (1).jpg",
        },
        {
          width: 1645,
          height: 1080,
          artist: "Atik Ishrak Chowdhury",
          url: "Atik Ishrak Chowdhury (2).jpg",
        },
        {
          width: 1440,
          height: 1080,
          artist: "Atik Ishrak Chowdhury",
          url: "Atik Ishrak Chowdhury (3).jpg",
        },
        {
          width: 1620,
          height: 1080,
          artist: "Farjana Ria",
          url: "Farjana Ria (1).jpg",
        },
        {
          width: 864,
          height: 1080,
          artist: "Farjana Ria",
          url: "Farjana Ria (2).jpg",
        },
        {
          width: 1620,
          height: 1080,
          artist: "Farjana Ria",
          url: "Farjana Ria (3).jpg",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.gallery-container {
  padding: 0 10vw;
  padding-top: 20vh;
}
.justified-item {
  img {
    max-width: 100%;
    position: relative;

    &:hover ~ .artist {
      opacity: 1;
    }
  }
  .artist {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.7);
    padding: 1em;
    opacity: 0;
    transition: 250ms opacity ease-out;

    &:hover {
      opacity: 1;
    }
  }
}
</style>