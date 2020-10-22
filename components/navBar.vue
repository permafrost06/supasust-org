<template>
  <div class="nav">
    <nuxt-link to="/" class="supa-font logo" aria-label="homepage"
      >SUPA</nuxt-link
    >
    <nav class="main-nav">
      <ul class="nav__list">
        <li class="nav__list-item">
          <nuxt-link to="/" class="nav__link">Viewfinder</nuxt-link>
        </li>
        <li class="nav__list-item">
          <nuxt-link to="/" class="nav__link">Gallery</nuxt-link>
        </li>
        <li class="nav__list-item">
          <nuxt-link to="/events" class="nav__link">Events</nuxt-link>
        </li>
        <li class="nav__list-item dropdown">
          <p class="nav__link no-underline">
            About Us <font-awesome-icon :icon="['fas', 'chevron-down']" />
          </p>
          <ul class="nav__list submenu">
            <li class="nav__list-item">
              <nuxt-link to="/activities" class="nav__link">Activities</nuxt-link>
            </li>
            <li class="nav__list-item">
              <nuxt-link to="/team" class="nav__link">Team</nuxt-link>
            </li>
            <li class="nav__list-item">
              <nuxt-link to="/advisors" class="nav__link">Advisors</nuxt-link>
            </li>
            <li class="nav__list-item">
              <nuxt-link to="/about" class="nav__link">About</nuxt-link>
            </li>
          </ul>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'navBar',
}
</script>

<style lang="scss" scoped>
.logo {
  font-size: 3em;
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
}

.nav__list {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
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
    content: '';
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
  cursor: pointer;
  position: relative;

  .no-underline::after {
    all: unset;
  }

  .no-underline:hover::after {
    all: unset;
  }

  &:hover > ul,
  ul:hover {
    visibility: visible;
  }

  ul {
    padding: 0.5em 0;
    visibility: hidden;
    position: absolute;
    width: 10em;
    display: flex;
    flex-direction: column;
    background: var(--background);

    li {
      padding: 0.5em 1em;
    }
  }
}
</style>