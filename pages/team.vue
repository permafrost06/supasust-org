<template>
  <div class="container">
    <section>
      <h1>Our Team</h1>
      <img class="full-width" src="~/assets/images/team-photo.jpg" alt="" />
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
          about: 'Department of Oceanography',
          flickr: 'https://www.flickr.com/photos/185360418@N06/',
          insta: 'shohan_220'
        },
        {
          id: 2,
          img: 'members/Sakeef Wahed.jpg',
          name: 'Sakeef Wahed',
          designation: 'Vice-President',
          about: 'Department of Petroleum and Mining Engineering'
        },
        {
          id: 3,
          img: 'members/Adila Zaman.jpg',
          name: 'Adila Zaman',
          designation: 'Vice-President',
          about: 'Department of Architecture',
          insta: 'adilazaman'
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
        {
          id: 6,
          img: 'members/Md. Moshiur Rahman.jpg',
          name: 'Md. Moshiur Rahman',
          designation: 'Assistant General Secretary',
        },
        {
          id: 7,
          img: 'members/Radia Islam.jpg',
          name: 'Radia Islam',
          designation: 'Chief Instructor',
        },
        {
          id: 8,
          img: 'members/Ahmed Fahimul Absar.jpg',
          name: 'Ahmed Fahimul Absar',
          designation: 'Trainer',
        },
        {
          id: 9,
          img: 'members/Gourab Saha.jpg',
          name: 'Gourab Saha',
          designation: 'Organizing Secretary',
        },
        {
          id: 10,
          img: 'members/Masud Rana Sarker.jpg',
          name: 'Masud Rana Sarker',
          designation: 'Assistant Organizing Secretary',
        },
        {
          id: 11,
          img: 'members/Rhythm Singha.jpg',
          name: 'Rhythm Singha',
          designation: 'Treasurer',
        },
        {
          id: 12,
          img: 'members/Atik Ishrak Chowdhury.jpg',
          name: 'Atik Ishrak Chowdhury',
          designation: 'Office Secretary',
        },
        {
          id: 13,
          img: 'members/Tanvin Mahtub Fariha.jpg',
          name: 'Tanvin Mahtub Fariha',
          designation: 'Head of Creative Field',
        },
        {
          id: 14,
          img: 'members/Tasnim Muna.jpg',
          name: 'Tasnim Muna',
          designation: 'Creative Field',
        },
        {
          id: 15,
          img: 'members/Tanak Dewan.jpg',
          name: 'Tanak Dewan',
          designation: 'Creative Field',
        },
        {
          id: 16,
          img: 'members/Rubayat Islam Rupak.jpg',
          name: 'Rubayat Islam Rupak',
          designation: 'Creative Field',
        },
        {
          id: 17,
          img: 'members/Simanta Joy.jpg',
          name: 'Simanta Joy',
          designation: 'Archieve Secretary',
        },
        // {
        //   id: 18,
        //   img: 'members/Tasrif Jamna Raiyan.jpg',
        //   name: 'Tasrif Jamna Raiyan',
        //   designation: 'Archieve Secretary',
        // },
        {
          id: 19,
          img: 'members/Galib Mahdi.jpg',
          name: 'Galib Mahdi',
          designation: 'Publication Secretary',
        },
        {
          id: 20,
          img: 'members/Pranto Roy.jpg',
          name: 'Pranto Roy',
          designation: 'Publication Secretary',
        },
        {
          id: 21,
          img: 'members/Richy Rubaiyat.jpg',
          name: 'Richy Rubaiyat',
          designation: 'Research Secretary',
        },
        {
          id: 22,
          img: 'members/Showrav Chowdhury.jpg',
          name: 'Showrav Chowdhury',
          designation: 'IT Secretary',
        },
        // {
        //   id: 23,
        //   img: 'members/Prottoy Ahmed.jpg',
        //   name: 'Prottoy Ahmed',
        //   designation: 'IT Secretary',
        // },
        {
          id: 24,
          img: 'members/Abu Bakkar Siddique.jpg',
          name: 'Abu Bakkar Siddique',
          designation: 'Public Relation Secretary',
        },
        {
          id: 25,
          img: 'members/Zunaid Pranto.jpg',
          name: 'Zunaid Pranto',
          designation: 'Film and Documentary Secretary',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  padding: 10vw;

  @media (max-width: 850px) {
    padding: 10vh 10vw;
  }
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
    
    @media (max-width: 990px) {
      grid-template-columns: repeat(2, 1fr);
    }
    
    @media (max-width: 660px) {
      grid-template-columns: repeat(1, 1fr);
    }
  }
}
</style>