<template>
    <section id="contact-us">
        <div class="section-title">
            <h2>Contact Us</h2>
            <span class="section-subtitle">Our postal adress and contact details</span>
            <img class="img-divider" src="../assets/img/header_divider.png" alt="styled divider">
        </div>
        <div class="contacts">
            <div class="contact" v-for="contact, i in contacts" :key="i">
                <img loading="lazy" :src="contact.image" :alt="contact.title">
                <h3> {{ contact.title }}</h3>
                <p> {{ contact.info1 }} </p>
                <p> {{ contact.info2 }} </p>
                <p> {{ contact.info3 }} </p>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppFooterContactUsSection',
    props: {
        contacts: Array,
    }
}
</script>

<style lang="scss" scoped>
    #contact-us {
        margin: 2rem auto;
        // title section
        .section-title {
            text-align: center;
            h2 {
                font-weight: lighter;
            }
            .section-subtitle {
                color: var(--clr-secondary-200);
            }
        }
        //contacts section
        .contacts {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 2rem;
            .contact {
                margin: 3rem 0;
                text-align: center;
                &:nth-child(2) p:nth-child(5) {
                    color: var(--clr-primary-600);
                    text-decoration: underline;
                }
            }
        }
    }

</style>