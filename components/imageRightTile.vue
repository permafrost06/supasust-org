<template>
    <div>
        <div class="container">
            <div class="description">
                <h2 class="h2-underline">Activity 1</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat id fugit, reprehenderit aperiam earum dolorum facilis modi tempora doloremque, commodi molestiae eligendi. Commodi esse eius impedit id distinctio incidunt ipsum.</p>
            </div>
            <img src="~/assets/images/vf-photo-2.jpg" alt="">
        </div>
    </div>
</template>

<script>
export default {
    name: 'imageRightTile',
    props: ['img', 'caption']
}
</script>

<style lang="scss" scoped>
.container {
    background-color: rgba(0, 0, 0, 0.51);
    display: flex;
    align-items: center;
}

img {
    width: 50vw;
    min-width: 30vw;
    object-fit: cover;
    padding: 1.5em;
}

.description {
    padding: 0 .5em 0 2em;
}

h2 {
    margin: 5px;
}
</style>