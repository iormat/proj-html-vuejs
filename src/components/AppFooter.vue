<template>
    <footer>
        <div class="container_small">
            <AppFooterContactUsSection
            :contacts="contactsArr"
            />

            <AppFooterFormSection/>
        </div>
    </footer>
</template>

<script>
import AppFooterContactUsSection from "./AppFooterContactUsSection.vue";
import AppFooterFormSection from "./AppFooterFormSection.vue";

export default {
    name: 'AppFooter',
    components: {
        AppFooterContactUsSection,
        AppFooterFormSection,
    },
    data() {
        return {
            contactsArr: [
                {
                    image: "./img/envelope (1).png",
                    title: "Postal Adress",
                    info1: "Fable Care 85",
                    info2: "Fentiman Ave Ottawa,",
                    info3: "ON K1S OT7",
                },
                {
                    image: "./img/mobile.png",
                    title: "Phone & E-mail",
                    info1: "Phone: 1-800-64-38",
                    info2: "Fax: 1-800-64-39",
                    info3: "office@fable.com",

                },
                {
                    image: "./img/clock.png",
                    title: "Business Hours",
                    info1: "Monday - Friday",
                    info2: "8.00 am - 5.00 pm",
                    info3: "Week-end Closed",
                },
                {
                    image: "./img/document (1).png",
                    title: "Sessions",
                    info1: "Mornings, 8 am - 12 noon",
                    info2: "Afternoons, 1 pm - 5 pm",
                    info3: "Full Day, 8 am - 5 pm",
                },
            ],
        }
    }
}
</script>

<style lang="scss" scoped>

</style>