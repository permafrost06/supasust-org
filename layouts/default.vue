<template>
  <div>
    <header>
      <navBar />
    </header>
    <Nuxt />
    <footer>
      <footerBar />
    </footer>
  </div>
</template>

<script>
import navBar from '../components/navBar'
import footerBar from '../components/footerBar'

export default {
  components: {
    navBar, footerBar
  },
  // head: {
  //    bodyAttrs: {
  //      'ontouchstart': ''
  //    }
  // }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

@font-face {
  font-family: 'bauhaus_93regular';
  src: url('~assets/fonts/bauhs93-webfont.woff') format('woff'),
    url('~assets/fonts/bauhs93-webfont.woff2') format('woff2');
}

html {
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  color: white;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

body {
  background-color: #202020;
}

h1 {
  padding: 0.5em 0;
}

@media (max-width: 620px) {
  h2 {
    font-size: 1em;
  }
}

.h2-underline:after {
  display: block;
  content: '';
  right: 5px;
  margin: 5px 0px;
  height: 3px;
  width: 12em;
  background: #ffffff;
  position: relative;
}

.h2-underline-center {
  display: inline-block;
  position: relative;
  padding-bottom: 2em;
}

.h2-underline-center:after {
  content: '';
  position: absolute;
  left: -3em;
  right: -3em;
  bottom: 0;
  top: 1.5em;
  height: 3px;
  background: #ffffff;
}

h4 {
  font-weight: 500;

  @media (max-width: 620px) {
    font-size: 0.75em;
  }
}

h5 {
  font-size: 1.5em;
  font-weight: 400;
}

p {
  padding: 1em 0;

  @media (max-width: 620px) {
    font-size: 1em;
  }

  &.no-padding {
    padding: 0;
  }
}

a {
  color: white;
  text-decoration: none;

  :hover {
    text-decoration: underline;
  }
}

.supa-font {
  font-family: 'bauhaus_93regular';
}

.description {
  margin: 10px 0px;
  margin-left: -5px;
}

.full-width {
  width: 100%;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>
