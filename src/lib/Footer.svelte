<script lang="ts">
    let year: number = new Date().getFullYear(); 
</script>

<footer class="footer">
    <div class="footer-item">
        <div class="footer-contact">Email: <a href="mailto:levi.bland@icloud.com" class="footer-link">levi.bland@icloud.com</a></div>
    </div>
    <div class="footer-item">
        &copy; {year} Levi Bland. All Rights Reserved.
    </div>
    <div class="footer-item">
        <div class="footer-contact">Tel: <a href="tel:+64272711452" class="footer-link">+64272711452</a></div>
    </div>
</footer>

<style lang="scss">
    @import '../styles/vars.scss';

    .footer {
        //position: absolute;
        //left: 0;
        width: 100%;
        padding: 3rem;
        background: $dark-dark;
        color: $gray;
        font-size: 1.6rem;
        text-align: center;
        font-family: $secondary-font;
        border-top: 1px solid $mid-dark;
        user-select: text;

        & .footer-item {
            display: inline-block;

            &:not(:last-child) {
                margin-right: 8rem;
            }

            @media only screen and (max-width: 50em) {
                display: block;

                &:not(:last-child) {
                    margin-right: 0;
                    margin-bottom: 1rem;
                }

                text-align: center;
            }
        }

        & .footer-contact {
            display: inline-block;

            &:not(:last-child) { margin-right: 3rem; }

            @media only screen and (max-width: 50em) {
                &:not(:last-child) {
                    margin-right: 3rem;
                    margin-bottom: .5rem;
                }
            }
        }

        & .footer-link {
            color: $white;
        }
    }
</style>