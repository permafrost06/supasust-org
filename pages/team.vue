<template>
  <div class="container">
    <section>
      <h1>Our Team</h1>
      <img class="full-width" src="~/assets/images/team-photo.jpg" alt="" />
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quisquam quam
        sit quidem, maiores expedita nemo eius molestias minima totam
        asperiores, modi pariatur? Obcaecati ratione totam vitae ea deserunt et
        magni. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quae
        molestias ut, incidunt in dicta culpa ipsum, rerum similique inventore
        porro, ea ab? Iste sunt nulla repudiandae sapiente cupiditate!
        Accusantium, voluptatibus. Lorem, ipsum dolor sit amet consectetur
        adipisicing elit. Optio, quaerat? Ipsum eveniet, sint quae iusto
        deleniti vitae ratione atque sunt aspernatur esse. Accusamus tempore sed
        commodi pariatur, sint eaque fugiat! Lorem ipsum dolor sit, amet
        consectetur adipisicing elit. Distinctio laudantium, incidunt officia,
        fugiat tenetur beatae dolores quisquam iure facilis error amet, aliquam
        illo ex maxime voluptatibus tempora laboriosam iusto soluta. Lorem ipsum
        dolor sit amet consectetur adipisicing elit. Veritatis architecto amet
        quisquam incidunt optio. Sint unde mollitia veritatis dolore
        necessitatibus eum quisquam, suscipit, ratione error deleniti ut? Minus,
        natus est? Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quo
        quaerat sequi alias repellendus fugiat, earum, nisi dolorum hic magnam
        debitis officiis perferendis dolores voluptatum ullam veniam fuga? Unde,
        quis ipsam?
      </p>
    </section>
    <section class="member-section">
      <h2 class="h2-underline-center">23rd Executive Committee</h2>
      <div class="member-list">
        <div v-for="member in members" v-bind:key="member.id">
          <member v-bind="member" />
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import member from '../components/member'
export default {
  components: member,
  data() {
    return {
      members: [
        {
          id: 1,
          img: 'members/Shohan Ur Rahaman.jpg',
          name: 'Shohan Ur Rahman',
          designation: 'President',
        },
        {
          id: 2,
          img: 'members/Sakeef Wahed.jpg',
          name: 'Sakeef Wahed',
          designation: 'Vice-President',
        },
        {
          id: 3,
          img: 'members/Adila Zaman.jpg',
          name: 'Adila Zaman',
          designation: 'Vice-President',
        },
        {
          id: 4,
          img: 'members/Mashfik Upal Aumy.jpg',
          name: 'Mashfik Upal Aumy',
          designation: 'Vice-President',
        },
        {
          id: 5,
          img: 'members/Prem Raj Saha.jpg',
          name: 'Prem Raj Saha',
          designation: 'General Secretary',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  padding: 10vw;
}

section {
  padding-bottom: 10vh;
}

.member-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-wrap: wrap;

  .member-list {
    display: grid;
    justify-content: space-evenly;
    gap: 0.5em;
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>