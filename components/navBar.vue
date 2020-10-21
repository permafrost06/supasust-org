<template>
  <div class="nav">
    <nuxt-link to="/" class="supa-font logo" aria-label="homepage">SUPA</nuxt-link>
      <nav class="main-nav">
        <ul class="nav__list">
          <li class="nav__list-item">
            <nuxt-link to="/" class="nav__link">Viewfinder</nuxt-link>
          </li>
          <li class="nav__list-item">
            <nuxt-link to="/" class="nav__link">Visual Fest</nuxt-link>
          </li>
          <li class="nav__list-item">
            <nuxt-link to="/" class="nav__link">Our Photographs</nuxt-link>
          </li>
          <li class="nav__list-item"><nuxt-link to="/" class="nav__link">About Us</nuxt-link></li>
        </ul>
      </nav>
  </div>
</template>

<script>
export default {
    name: 'navBar'
}
</script>

<style lang="scss" scoped>
.logo {
  font-size: 3em;
}

.nav {
  --text: #f4f4f4;
  --text-inverse: #333;
  --background: rgba(0, 0, 0, 0.51);

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

  &--btn {
    border: 1.5px solid currentColor;
    border-radius: 2em;
    margin-left: 1em;
    transition: background 250ms ease-in-out;
    letter-spacing: 1px;
    padding: 0.75em 1.5em;

    &:hover {
      background: var(--text);
      color: var(--text-inverse);
      border-color: var(--text);
    }

    &::after {
      display: none;
    }

    &--highlight {
      background: limegreen;
      border-color: limegreen;
      color: #333;

      &:hover {
        background: var(--text);
        border-color: var(--text);
      }
    }
  }
}
</style>