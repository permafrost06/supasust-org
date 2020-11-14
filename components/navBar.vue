<template>
  <div class="nav">
    <nuxt-link to="/" class="supa-font logo">SUPA</nuxt-link>
    <nav :class="[{'nav-active':navActive}, 'main-nav']">
      <ul class="nav__list">
        <li class="nav__list-item" v-for="item in nav_items" :key="item.name">
          <nuxt-link
            :to="item.link"
            class="nav__link"
            v-if="item.type == 'internal'"
            >{{ item.name }}</nuxt-link
          >
          <a
            :href="item.link"
            class="nav__link"
            v-if="item.type == 'external'"
            >{{ item.name }}</a
          >
        </li>
        <li class="nav__list-item dropdown" v-if="dropdown">
            {{ dropdown_name }}
            <font-awesome-icon :icon="['fas', 'chevron-down']" />
          <ul class="nav__list submenu">
            <li
              class="nav__list-item"
              v-for="item in dropdown_items"
              :key="item.name"
            >
              <nuxt-link :to="item.link" class="nav__link">{{
                item.name
              }}</nuxt-link>
            </li>
          </ul>
        </li>
      </ul>
    </nav>
    <div @click="navActive = !navActive" class="nav-toggle-label">
      <span></span>
    </div>
  </div>
</template>

<script>
// import * as Hammer from 'hammerjs'

// Vue.directive("tap", {
// 	bind: function(el, binding) {
// 		if (typeof binding.value === "function") {
// 			const mc = new Hammer(el);
// 			mc.on("tap", binding.value);
// 		}
// 	}
// });

export default {
  name: "navBar",
  data() {
    return {
      navActive: false,
      dropdownActive: false,
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
      ],
      dropdown: true,
      dropdown_name: "About Us",
      dropdown_items: [
        {
          name: "Activities",
          type: "internal",
          link: "/activities",
        },
        {
          name: "Team",
          type: "internal",
          link: "/team",
        },
        {
          name: "Advisors",
          type: "internal",
          link: "/advisors",
        },
        {
          name: "About",
          type: "internal",
          link: "/about",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.logo {
  font-size: 3em;

  @media (max-width: 800px) {
    font-size: 2em;
  }
}

.nav-toggle-label {
  position: absolute;
  top: 0;
  left: 0;
  margin-left: 5vw;
  height: 100%;
  display: flex;
  align-items: center;
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
}

.nav-toggle-label span::before,
.nav-toggle-label span::after {
  content: "";
  position: absolute;
}

.nav-toggle-label span::before {
  bottom: 7px;
}

.nav-toggle-label span::after {
  top: 7px;
}

.nav-active {
  visibility: visible;
  opacity: 1;
}

@media screen and (min-width: 800px) {
  .nav-toggle-label {
    display: none;
  }
}

// .sub-nav-toggle:checked + label + ul {
//   visibility: visible;
//   opacity: 1;
// }

@media (max-width: 800px) {
  nav {
    opacity: 0;
    visibility: hidden;
    transition: opacity 250ms ease-in;
  }
}

.nav {
  --text: #f4f4f4;
  --text-inverse: #333;
  --background: rgba(0, 0, 0, 1);

  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 999;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5em 10vw;
  transition: background 250ms ease-in;
  background: var(--background);
  color: var(--text);

  @media (max-width: 800px) {
    display: block;
    text-align: center;
    padding: 1em 5vw;
  }
}

.nav__list {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;

  @media (max-width: 800px) {
    position: absolute;
    flex-direction: column;
    text-align: center;
    top: 100%;
    left: 0;
    width: 100%;
    background: var(--background);

    .nav__link {
      padding: 1em 0;
    }
  }
}

.nav__link {
  --spacing: 1em;
  text-decoration: none;
  color: inherit;
  display: inline-block;
  padding: calc(var(--spacing) / 2) var(--spacing);
  position: relative;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: 0.9rem;

  &:after {
    content: "";
    position: absolute;
    bottom: 0;
    left: var(--spacing);
    right: var(--spacing);
    height: 2px;
    background: currentColor;
    transform: scaleX(0);
    transition: transform 150ms ease-in-out;
  }

  &:hover::after {
    transform: scaleX(1);
  }
}

.dropdown {
  --spacing: 1em;
  cursor: pointer;
  text-decoration: none;
  color: inherit;
  display: inline-block;
  padding: calc(var(--spacing) / 2) var(--spacing);
  position: relative;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: 0.9rem;

  .no-underline::after {
    all: unset;
  }

  .no-underline:hover::after {
    all: unset;
  }

  &:hover > ul,
  ul:hover {
    visibility: visible;
    opacity: 100%;
  }

  .dropdown-active {
    visibility: visible;
    opacity: 100%;
  }

  ul {
    padding: 0.5em 0;
    visibility: hidden;
    opacity: 0;
    position: absolute;
    width: 10em;
    display: flex;
    flex-direction: column;
    background: var(--background);
    transition: all 0.5s ease;

    @media (max-width: 800px) {
      width: 100%;
    }

    li {
      padding: 0 1em;
    }
  }
}
</style>