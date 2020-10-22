<template>
    <div class="container">
        <h1>Our Advisors</h1>
        <div v-for="advisor in advisors" v-bind:key="advisor.id">
            <quoteImageLeft v-if="advisor.id % 2 != 0" v-bind="advisor" />
            <quoteImageRight v-if="advisor.id % 2 == 0" v-bind="advisor" />
        </div>
    </div>
</template>

<script>
import quoteImageLeft from '../components/quoteImageLeft'
import quoteImageRight from '../components/quoteImageRight'

export default {
    components: {
        quoteImageLeft, quoteImageRight
    },
    data() {
        return {
            advisors: [
                {
                    id: 1,
                    img: 'advisors/advisor-1.jpg',
                    quote: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat id fugit, reprehenderit aperiam earum dolorum facilis modi tempora doloremque, commodi molestiae eligendi. Commodi esse eius impedit id distinctio incidunt ipsum.',
                    author: 'Advisor One',
                    designation: 'Lecturer'
                },
                {
                    id: 2,
                    img: 'advisors/advisor-2.jpg',
                    quote: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat id fugit, reprehenderit aperiam earum dolorum facilis modi tempora doloremque, commodi molestiae eligendi. Commodi esse eius impedit id distinctio incidunt ipsum.',
                    author: 'Advisor two',
                    designation: 'Assistant Professor'
                },
                {
                    id: 3,
                    img: 'advisors/advisor-3.jpg',
                    quote: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat id fugit, reprehenderit aperiam earum dolorum facilis modi tempora doloremque, commodi molestiae eligendi. Commodi esse eius impedit id distinctio incidunt ipsum.',
                    author: 'Advisor Three',
                    designation: 'Professor'
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
.container {
    padding: 10vw;

    &>div {
        padding: 2em 0;
    }
}
</style>