<template>
    <div class="footer-container">
        <div class="dev">Website developed by <a href="#">FinalConcept Media</a><br />Hosted at <a href="#">SYNC
                SERVE</a>
        </div>
        <div class="footer-right">
            <h2>Contact</h2>
            <ul class="contact">
                <li>Room No: 102, Physical Centre, SUST, Sylhet-3114</li>
                <li><a href="#">+880 1915-076164</a></li>
                <li><a href="#">supa@sust.edu</a></li>
            </ul>
            <ul class="socials">
                <li><a href="#"><i class="fab fa-instagram-square fa-2x" /></a>
                </li>
                <li><a href="#"><i class="fab fa-facebook-square fa-2x" /></a>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'footerBar'
}
</script>

<style lang="scss" scoped>
.footer-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 5vh 7em;
    background-color: rgba(0, 0, 0, 1);

    ul {
        list-style: none;
        margin: 0;
        padding: 0;

        li {
            padding: .25em 0;
        }
    }

    .footer-right {
        text-align: right;
    }
}
</style>