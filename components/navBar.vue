<template>
  <header>
    <h1 @click="closeNav" class="supa-font logo"><nuxt-link to="/" exact>SUPA</nuxt-link></h1>
    <nav :class="{'nav-visible':navVisible}">
      <ul>
        <li class="nav__list-item" @click="closeNav" v-for="item in nav_items" :key="item.name">
          <nuxt-link
            :to="item.link"
            :class="{'nav-link-visible':navVisible}"
            v-if="item.type == 'internal'"
            >{{ item.name }}</nuxt-link
          >
          <a
            :href="item.link"
            :class="{'nav-link-visible':navVisible}"
            v-if="item.type == 'external'"
            target="_blank"
            >{{ item.name }}</a
          >
        </li>
      </ul>
    </nav>
    <label :class="{'cross': navVisible}" @click="toggleNav" class="nav-toggle-label">
      <span></span>
    </label>
  </header>
</template>

<script>
export default {
  data() {
    return {
      navVisible: false,
      nav_items: [
        {
          name: "Viewfinder",
          type: "external",
          link: "https://viewfinder.supasust.org/",
        },
        {
          name: "Gallery",
          type: "internal",
          link: "/gallery",
        },
        {
          name: "Events",
          type: "internal",
          link: "/events",
        },
        {
          name: "About Us",
          type: "internal",
          link: "/about"
        }
      ],
    };
  },
  methods: {
    toggleNav() {
      this.navVisible = !this.navVisible;
    },
    closeNav() {
      this.navVisible = false;
    }
  }
};
</script>

<style lang="scss">

.nav-toggle-label {
  position: absolute;
  top: 0;
  left: 0;
  margin-left: 1em;
  height: 100%;
  display: flex;
  align-items: center;
  cursor: pointer;
}

.nav-toggle-label span,
.nav-toggle-label span::before,
.nav-toggle-label span::after {
  display: block;
  background: white;
  height: 2px;
  width: 2em;
  border-radius: 2px;
  position: relative;
  transition: all .5s ease-in-out;
}

.nav-toggle-label span::before,
.nav-toggle-label span::after {
  content: '';
  position: absolute;
}

.nav-toggle-label span::before {
  transform: translateY(-7px);
}

.nav-toggle-label span::after {
  transform: translateY(7px);
}

.cross span {
  background: transparent;
  transform: translateY(50px);
}

.cross span::before {
  transform: rotate(45deg) translate(-35px, -35px);
}

.cross span::after {
  transform: rotate(135deg) translate(-35px, 35px);
}

/* navigation styles start here */

.logo {
  font-weight: 300;
}

header {
  background: rgba(0, 0, 0, 1);
  text-align: center;
  z-index: 999;
  position: absolute;
  width: 100%;
}

nav {
  position: absolute;
  text-align: left;
  top: 100%;
  left: 0;
  background: rgba(0, 0, 0, 1);
  width: 100%;
  transform: scale(1, 0);
  transform-origin: top;
  transition: transform 400ms ease-in-out;
}

nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav li {
  margin-bottom: 1em;
  margin-left: 1em;
}

nav a {
  color: white;
  text-decoration: none;
  font-size: 0.9rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  opacity: 0;
  transition: opacity 150ms ease-in-out;
}

nav a:hover {
  color: #888;
}

.nav-visible {
  transform: scale(1,1);
}

.nav-link-visible {
  opacity: 1;
  transition: opacity 250ms ease-in-out 250ms;
}

@media screen and (min-width: 800px) {
  .nav-toggle-label {
    display: none;
  }

  header {
    display: grid;
    grid-template-columns: 10vw auto minmax(600px, 3fr) 10vw;
  }

  .logo {
    grid-column: 2 / 3;
    font-size: 3em;
  }

  nav {
    // all: unset; /* this causes issues with Edge, since it's unsupported */

    /* the following lines are not from my video, but add Edge support */
    position: relative;
    text-align: left;
    transition: none;
    transform: scale(1,1);
    background: none;
    top: initial;
    left: initial;
    /* end Edge support stuff */

    grid-column: 3 / 4;
    display: flex;
    justify-content: flex-end;
    align-items: center;
  }

  nav ul {
    display: flex;
  }

  nav li {
    margin-left: 3em;
    margin-bottom: 0;
  }

  nav a {
    opacity: 1;
    position: relative;
  }

  nav a::after {
    content: '';
    display: block;
    height: 2px;
    background: white;
    position: absolute;
    bottom: -.75em;
    left: 0;
    right: 0;
    transform: scale(0, 1);
    transition: transform ease-out 150ms;
  }

  nav a:hover::after,
  .nuxt-link-active::after {
    transform: scale(1,1);
  }
}

.nuxt-link-active {
  font-weight: bold;
}
</style>
