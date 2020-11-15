<template>
  <div class="container">
    <h1>Our Advisors</h1>
    <div v-for="advisor in advisors" v-bind:key="advisor.id">
      <quoteImageLeft v-if="advisor.id % 2 != 0" v-bind="advisor" />
      <quoteImageRight v-if="advisor.id % 2 == 0" v-bind="advisor" />
    </div>
    <div class="member-list">
      <div v-for="member in members" v-bind:key="member.id">
        <member v-bind="member" />
      </div>
    </div>
  </div>
</template>

<script>
import member from '../components/member'

export default {
  components: {
    member
  },
  data() {
    return {
      members: [
        {
          id: 1,
          img: 'advisors/advisor-1sq.jpg',
          name: 'A K M Mazharul Islam',
          designation: 'Professor, Department of Anthropology',
        },
        {
          id: 2,
          img: 'advisors/advisor-2sq.jpg',
          name: 'Md Mahmud Hasan',
          designation: 'Assistant Professor, Department of Public Administration',
        },
        {
          id: 3,
          img: 'advisors/advisor-3sq.jpg',
          name: 'Shafaet Ahmed',
          designation: 'Assistant Professor, Department of Food Engineering and Tea Technology',
        },
        {
          id: 4,
          img: 'advisors/advisor-4sq.jpg',
          name: 'Hossain Mohammad Nahyan',
          designation: 'Assistant Professor, Department of Architecture',
        },
        {
          id: 5,
          img: 'advisors/advisor-5sq.jpg',
          name: 'Shetu Akter',
          designation: 'Lecturer, Department of Geography and Environment',
        }
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

  & > div {
    padding: 2em 0;
  }
}

.member-list {
display: grid;
justify-content: space-evenly;
gap: 0.5em;
grid-template-columns: repeat(3, 1fr);
}
</style>