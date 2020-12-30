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
import member from "../components/member";
export default {
  components: member,
  data() {
    return {
      members: [
        {
          id: 1,
          img: "members/Shohan Ur Rahaman.jpg",
          name: "Shohan Ur Rahman",
          designation: "President",
          about: "Department of Oceanography",
          flickr: "https://www.flickr.com/photos/185360418@N06/",
          insta: "shohan_220",
        },
        {
          id: 2,
          img: "members/Adila Zaman.jpg",
          name: "Adila Zaman",
          designation: "Vice President",
          about: "Department of Architecture",
          insta: "adilazaman",
        },
        {
          id: 3,
          img: "members/Mashfik Upal Aumy.jpg",
          name: "Mashfik Upal Aumy",
          designation: "Vice President",
          about: "Department of Food Engineering & Tea Technology",
          flickr: "https://www.flickr.com/photos/188574907@N04/",
          insta: "mashfik.aumy",
        },
        {
          id: 4,
          img: "members/Sakeef Wahed.jpg",
          name: "Sakeef Wahed",
          designation: "Vice President",
          about: "Department of Petroleum & Mining Engineering",
          flickr: "",
          insta: "",
        },
        {
          id: 5,
          img: "members/Prem Raj Saha.jpg",
          name: "Prem Raj Saha",
          designation: "General Secretary",
          about: "Department of Food Engineering & Tea Technology",
          flickr: "",
          insta: "",
        },
        {
          id: 6,
          img: "members/Md. Moshiur Rahman.jpg",
          name: "Md. Moshiur Rahman",
          designation: "Assistant General Secretary",
          about: "Department of English",
          flickr: "",
          insta: "shaishob_71",
        },
        {
          id: 7,
          img: "members/Radia Islam.jpg",
          name: "Radia Islam",
          designation: "Chief Instructor",
          about: "Department of English",
          flickr: "https://www.flickr.com/photos/189243252@N07/",
          insta: "radia_islam",
        },
        {
          id: 8,
          img: "members/Ahmed Fahimul Absar.jpg",
          name: "Ahmad Fahimul Absar",
          designation: "Trainer",
          about: "Department of Architecture",
          flickr: "https://www.flickr.com/photos/ahmadfahimulabsar/",
          insta: "ahmad.fahimul.absar",
        },
        {
          id: 9,
          img: "members/Gourab Saha.jpg",
          name: "Gourab Saha",
          designation: "Organizing Secretary",
          about: "Department of Geography and Environmenty",
          flickr: "https://www.flickr.com/photos/187903096@N05/",
          insta: "gsaha.bd",
        },
        {
          id: 10,
          img: "members/Masud Rana Sarker.jpg",
          name: "Masud Rana Sarkaar",
          designation: "Assistant Organizing Secretary",
          about: "Department of Statistics",
          flickr: "",
          insta: "",
        },
        {
          id: 11,
          img: "members/Rhythm Singha.jpg",
          name: "Rhythm Singha",
          designation: "Finance Secretary",
          about: "Department of Food Engineering & Tea Technology",
          flickr: "",
          insta: "rhythm_singha",
        },
        {
          id: 12,
          img: "members/Atik Ishrak Chowdhury.jpg",
          name: "Atik Ishrak Sumit",
          designation: "Office Secretary",
          about: "Department of Architecture",
          flickr: "https://www.flickr.com/ishrakSumit",
          insta: "atik_ishrak_bd",
        },
        {
          id: 13,
          img: "members/Tanvin Mahtub Fariha.jpg",
          name: "Tanvin Mahtub Fariha",
          designation: "Head of Creative Field",
          about: "Department of Architecture",
          flickr: "",
          insta: "fariha_adhora",
        },
        {
          id: 14,
          img: "members/Rubayat Islam Rupak.jpg",
          name: "Rubayat Islam Rupak",
          designation: "Creative Field",
          about: "Department of Architecture",
          flickr: "",
          insta: "rubayat_rupak",
        },
        {
          id: 15,
          img: "members/Tasnim Muna.jpg",
          name: "Tasnim Muna",
          designation: "Creative Field",
          about: "Department of Business Admininstration",
          flickr: "",
          insta: "",
        },
        {
          id: 16,
          name: "Tanak Dewan",
          designation: "Creative Field",
          about: "Department of Anthropolgy",
          flickr: "",
          insta: "tan_ak47",
        },
        {
          id: 17,
          img: "members/Simanta Joy.jpg",
          name: "Simanta Joy",
          designation: "Archive Secretary",
          about: "Department of English",
          flickr: "",
          insta: "simantajoy",
        },
        {
        id: 18,
            img: 'members/Tasrif Jaman Raiyan.JPG',
            name: 'Tasrif Jaman Raiyan',
            designation: 'Archive Secretary',
            about: 'Department of Statistics',
            flickr: '',
            insta: 'ra_iyaan'
        },
        {
          id: 19,
          img: "members/Galib Mahdi.jpg",
          name: "Galib Mahdi",
          designation: "Publicity Secretary",
          about: "Department of Economics",
          flickr: "",
          insta: "galib_mahdi",
        },
        {
          id: 20,
          img: "members/Pranto Roy.jpg",
          name: "Pranto Roy",
          designation: "Publication Secretary",
          about: "Department of Oceanography",
          flickr: "",
          insta: "pranto_roy_1",
        },
        {
          id: 21,
          img: "members/Richy Rubaiyat.jpg",
          name: "Kaniz Rubaiyat Richy",
          designation: "Research Secretary",
          about: "Department of Petroleum & Mining Engineering",
          flickr: "",
          insta: "riiichyyyyy",
        },
        {
          id: 22,
          img: "members/Abu Bakkar Siddique.jpg",
          name: "Abu Bakkar Siddique",
          designation: "Public Relation Secretary",
          about: "Department of Petroleum & Mining Engineering",
          flickr: "",
          insta: "ab_siddiqu3",
        },
        {
          id: 23,
          img: "members/Showrav Chowdhury.jpg",
          name: "Showrav Chowdhury",
          designation: "IT Secretary",
          about: "Department of English",
          flickr: "https://www.flickr.com/photos/showrav_me/",
          insta: "showrav_bd",
        },
        {
          id: 24,
          name: "Prottoy Ahmed",
          designation: "IT Secretary",
          about: "Department of Software Engineering",
          flickr: "",
          insta: "",
        },
        {
          id: 25,
          name: "Zunaid Pranto",
          designation: "Film and Documentary Secretary",
          about: "Department of Architecture",
          flickr: "",
          insta: "whateverzunaid",
        },
      ],
    };
  },
};
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