<template>
  <div class="container">
    <div class="slider">
      <div class="slide current">
        <div class="content">
          <h1>Slide One</h1>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit hic
            maxime, voluptatibus labore doloremque vero!
          </p>
        </div>
      </div>
      <div class="slide">
        <div class="content">
          <h1>Slide Two</h1>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit hic
            maxime, voluptatibus labore doloremque vero!
          </p>
        </div>
      </div>
      <div class="slide">
        <div class="content">
          <h1>Slide Three</h1>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit hic
            maxime, voluptatibus labore doloremque vero!
          </p>
        </div>
      </div>
      <div class="slide">
        <div class="content">
          <h1>Slide Four</h1>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit hic
            maxime, voluptatibus labore doloremque vero!
          </p>
        </div>
      </div>
      <div class="slide">
        <div class="content">
          <h1>Slide Five</h1>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit hic
            maxime, voluptatibus labore doloremque vero!
          </p>
        </div>
      </div>
      <div class="slide">
        <div class="content">
          <h1>Slide Six</h1>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit hic
            maxime, voluptatibus labore doloremque vero!
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'carousel'
//   mounted: () => {
//       const slides = document.querySelectorAll('.slide');
//         // const next = document.querySelector('#next');
//         // const prev = document.querySelector('#prev');
//         const auto = false; // Auto scroll
//         const intervalTime = 5000;
//         let slideInterval;

//         const nextSlide = () => {
//         // Get current class
//         const current = document.querySelector('.current');
//         // Remove current class
//         current.classList.remove('current');
//         // Check for next slide
//         if (current.nextElementSibling) {
//             // Add current to next sibling
//             current.nextElementSibling.classList.add('current');
//         } else {
//             // Add current to start
//             slides[0].classList.add('current');
//         }
//         setTimeout(() => current.classList.remove('current'));
//         };

//         const prevSlide = () => {
//         // Get current class
//         const current = document.querySelector('.current');
//         // Remove current class
//         current.classList.remove('current');
//         // Check for prev slide
//         if (current.previousElementSibling) {
//             // Add current to prev sibling
//             current.previousElementSibling.classList.add('current');
//         } else {
//             // Add current to last
//             slides[slides.length - 1].classList.add('current');
//         }
//         setTimeout(() => current.classList.remove('current'));
//         };

//         // Button events
//         next.addEventListener('click', e => {
//         nextSlide();
//         if (auto) {
//             clearInterval(slideInterval);
//             slideInterval = setInterval(nextSlide, intervalTime);
//         }
//         });

//         prev.addEventListener('click', e => {
//         prevSlide();
//         if (auto) {
//             clearInterval(slideInterval);
//             slideInterval = setInterval(nextSlide, intervalTime);
//         }
//         });

//         // Auto slide
//         if (auto) {
//         // Run next slide at interval time
//         slideInterval = setInterval(nextSlide, intervalTime);
//         }

//         }
    }
</script>

<style lang="scss" scoped>
.container {
  position: relative;
}

.slider {
  position: relative;
  overflow: hidden;
  height: 80vh;
//   width: 10vw;
}

.slide {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 0.4s ease-in-out;
}

.slide.current {
  opacity: 1;
}

.slide .content {
  position: absolute;
  bottom: 0;
  left: -55%;
  opacity: 0;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.51);
  color: #fff;
  padding: 35px;
}

.slide .content h1 {
  margin-bottom: 10px;
}

.slide.current .content {
  opacity: 1;
  transform: translateX(600px);
  transition: opacity 0.7s ease-in-out 0.3s;
}

.buttons button#next {
  position: absolute;
  top: 40%;
  left: 200px;
}

.buttons button#prev {
  position: absolute;
  top: 40%;
  left: 15px;
}

.buttons button {
  border: 2px solid #fff;
  background-color: transparent;
  color: #fff;
  cursor: pointer;
  padding: 13px 15px;
  border-radius: 50%;
  outline: none;
}

.buttons button:hover {
  background-color: #fff;
  color: #333;
}

@media (max-width: 500px) {
  .slide .content {
    bottom: -300px;
    left: 0;
    width: 100%;
  }

  .slide.current .content {
    transform: translateY(-300px);
  }
}

/* Backgorund Images */

.slide:first-child {
  background: url('https://source.unsplash.com/RyRpq9SUwAU/1600x900') no-repeat
    center top/cover;
}
.slide:nth-child(2) {
  background: url('https://source.unsplash.com/BeOW_PJjA0w/1600x900') no-repeat
    center top/cover;
}
.slide:nth-child(3) {
  background: url('https://source.unsplash.com/TMOeGZw9NY4/1600x900') no-repeat
    center top/cover;
}
.slide:nth-child(4) {
  background: url('https://source.unsplash.com/yXpA_eCbtzI/1600x900') no-repeat
    center top/cover;
}
.slide:nth-child(5) {
  background: url('https://source.unsplash.com/ULmaQh9Gvbg/1600x900') no-repeat
    center top/cover;
}
.slide:nth-child(6) {
  background: url('https://source.unsplash.com/ggZuL3BTSJU/1600x900') no-repeat
    center center/cover;
}
</style>