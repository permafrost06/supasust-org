<template>
  <div class="container">
    <section>
      <h1>Our Team</h1>
      <img class="full-width" src="~/assets/images/team-photo.jpg" alt="" />
    </section>
    <section class="member-section">
      <h2 class="h2-underline-center">24th Executive Committee</h2>
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
          img: "members/Radia Islam.jpg",
          name: "Radia Islam",
          designation: "President",
          about: "Department of English",
          flickr: "",
          insta: "",
        },
        {
          id: 2,
          img: "members/Muammer Galib Mahdi.jpg",
          name: "Muammer Galib Mahdi",
          designation: "Vice President",
          about: "Department of Economics",
          flickr: "",
          insta: "galib_mahdi",
        },
        {
          id: 3,
          img: "members/Md. Moshiur Rahman.jpg",
          name: "Md. Moshiur Rahman",
          designation: "General Secretary",
          about: "Department of English",
          flickr: "",
          insta: "shaishob_71",
        },
        {
          id: 4,
          img: "members/Showrav Chowdhury.jpg",
          name: "Showrav Chowdhury",
          designation: "Assistant General Secretary",
          about: "Department of English",
          flickr: "https://www.flickr.com/photos/showrav_me/",
          insta: "showrav_photos",
        },
        {
          id: 5,
          img: "members/Abu Bakker Siddique.jpg",
          name: "Abu Bakker Siddique",
          designation: "Assistant General Secretary",
          about: "Department of Petroleum & Mining Engineering",
          flickr: "",
          insta: "",
        },
        {
          id: 6,
          img: "members/Ahmad Fahimul Absar.jpg",
          name: "Ahmad Fahimul Absar",
          designation: "Chief Instructor",
          about: "Department of Architecture",
          flickr: "",
          insta: "ahmad_fahimul_absar",
        },
        {
          id: 7,
          img: "members/Tasnim Binte Abdur Rahim Muna.jpg",
          name: "Tasnim Binte Abdur Rahim Muna",
          designation: "Trainer & Research Secretary",
          about: "Department of BBA",
          flickr: "",
          insta: "",
        },
        {
          id: 8,
          img: "members/Tasrif Jaman Raiyan.jpg",
          name: "Tasrif Jaman Raiyan",
          designation: "Organizing Secretary",
          about: "Department of Statistics",
          flickr: "",
          insta: "ra_iyaan",
        },
        {
          id: 9,
          img: "members/Pranto Roy.jpg",
          name: "Pranto Roy",
          designation: "Finance Secretary",
          about: "Department of Oceanography",
          flickr: "",
          insta: "",
        },

        {
          id: 10,
          img: "members/Tanak Dewan.jpg",
          name: "Tanak Dewan",
          designation: "Office Secretary",
          about: "Department of Anthropology",
          flickr: "",
          insta: "",
        },
        {
          id: 11,
          img: "members/Kaniz Rubaiyat Richy.jpg",
          name: "Kaniz Rubaiyat Richy",
          designation: "Publicity Secretary",
          about: "Department of Petroleum & Mining Engineering",
          flickr: "",
          insta: "rubaiyat_richy",
        },
        {
          id: 12,
          img: "members/Zunaid Mostafa Pranto.jpg",
          name: "Zunaid Mostafa Pranto",
          designation: "Publicity Secretary",
          about: "Department of Architecture",
          flickr: "",
          insta: "",
        },
        {
          id: 13,
          img: "members/Rubayat Islam Rupak.jpg",
          name: "Rubayat Islam Rupak",
          designation: "Design Executive",
          about: "Department of Architecture",
          flickr: "",
          insta: "rubayat_rupak",
        },

        {
          id: 14,
          img: "members/Simanta Joy.jpg",
          name: "Simanta Goswami Joy",
          designation: "Exhibition Executive",
          about: "Department of English",
          flickr: "",
          insta: "simantajoy",
        },
        {
          id: 15,
          img: "members/Md Asadullah.jpg",
          name: "Md Asadullah",
          designation: "Executive Committee Member",
          about: "Department of Sociology",
          flickr: "",
          insta: "",
        },

        {
          id: 16,
          img: "members/Md.Anisul Garibin chowdhury.jpg",
          name: "Md.Anisul Garibin chowdhury",
          designation: "Executive Committee Member",
          about: "Department of Statistics",
          flickr: "",
          insta: "anisul_garibin",
        },
        {
          id: 17,
          img: "members/Ashiqur Rahman Sakib.jpg",
          name: "Ashiqur Rahman Sakib",
          designation: "Executive Committee Member",
          about: "Department of Oceanography",
          flickr: "",
          insta: "sak_ib_200.6",
        },

        {
          id: 18,
          img: "members/Saba Raidah Faruquee.jpg",
          name: "Saba Raidah Faruquee",
          designation: "Executive Committee Member",
          about: "Department of Architecture",
          flickr: "",
          insta: "1tough_act2follow",
        },
        {
          id: 19,
          img: "members/Md. Aqib Khan.jpg",
          name: "Md. Aqib Khan",
          designation: "Executive Committee Member",
          about: "Department of Architecture",
          flickr: "",
          insta: "hung_ry_potato",
        },
        {
          id: 20,
          img: "members/Azharul Islam.jpg",
          name: "Azharul Islam",
          designation: "Executive Committee Member",
          about: "Department of Social Work",
          flickr: "",
          insta: "_azhar33",
        },
        {
          id: 21,
          img: "members/Aniqa Zahin.jpg",
          name: "Aniqa Zahin",
          designation: "Executive Committee Member",
          about: "Department of Architecture",
          flickr: "",
          insta: "azure_80",
        },
        {
          id: 22,
          img: "members/Mohammad Naimul Islam.jpg",
          name: "Mohammad Naimul Islam",
          designation: "Executive Committee Member",
          about: "Department of Architecture",
          flickr: "",
          insta: "naimulislammridul",
        },
        {
          id: 23,
          img: "members/Sanjida Afrin Jeem.jpg",
          name: "Sanjida Afrin Jeem",
          designation: "Executive Committee Member",
          about: "Department of Architecture",
          flickr: "",
          insta: "",
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
