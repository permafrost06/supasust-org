<template>
    <div class="container">
        <h1>Events</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Et provident repudiandae inventore perferendis impedit sunt aliquam quisquam quas! Hic quaerat magni earum vel. Est soluta voluptatum molestiae eveniet, sequi aspernatur. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Odit, necessitatibus placeat ex vitae suscipit aliquid eius natus veritatis sunt, facilis ea repellat explicabo beatae, unde quaerat architecto. Odio, nostrum laborum.</p>
        <imageLeftTile />
        <imageRightTile />
        <imageLeftTile />
    </div>
</template>

<script>
import imageLeftTile from '../components/imageLeftTile'
import imageRightTile from '../components/imageRightTile'

export default {
    components: {
        imageLeftTile, imageRightTile
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