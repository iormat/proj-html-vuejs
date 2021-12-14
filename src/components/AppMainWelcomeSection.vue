<template>
    <section id="welcome-section" class="container_small">
        <!-- section header -->
        <div class="section-title">
            <h2>Welcome to Fable</h2>
            <span class="section-subtitle">Fable daycare&comma; preschool&comma; and kindergarten</span>
            <img class="img-divider" src="../assets/img/header_divider.png" alt="styled divider">
        </div>
        <!-- section main -->
        <div class="section-main">
            <div class="welcome-card" v-for="welcomeCard, i in welcomeCardsArr" :key="i">
                <div class="image-container">
                    <img :src="welcomeCard.image" :alt="welcomeCard.title">
                </div>
                <h3>{{ welcomeCard.title }}</h3>
                <p>{{ welcomeCard.text }}</p>
            </div>
        </div>
    </section>
</template>


<script>
export default {
    name: 'AppMainWelcomeSection',
    data() {
        return {
            // emulate API call
            welcomeCardsArr: [
                {
                    image: "./img/schoolbag_alt.png",
                    title: "Morbi Etos",
                    text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Consequuntur nihil expedita placeat nobis aperiam sunt vel itaque, natus sequi corrupti."
                },
                {
                    image: "./img/stroller_alt.png",
                    title: "Congue Gravida",
                    text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Consequuntur nihil expedita placeat nobis aperiam sunt vel itaque, natus sequi corrupti."
                },
                {
                    image: "./img/globe_alt.png",
                    title: "Maecenas Node",
                    text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Consequuntur nihil expedita placeat nobis aperiam sunt vel itaque, natus sequi corrupti."
                },
                {
                    image: "./img/bell_alt.png",
                    title: "Praesent Morbi",
                    text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Consequuntur nihil expedita placeat nobis aperiam sunt vel itaque, natus sequi corrupti."
                },
            ],
        }
    }
}
</script>

<style scoped lang="scss">
#welcome-section {
    margin: 3rem auto;
    // title section rules
    .section-title {
        text-align: center;
        h2 {
             font-weight: 300;
        }
        .section-subtitle {
            color: var(--clr-secondary-200);
        }
    }
    // main section rules
    .section-main {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 2rem;
        .welcome-card {
            margin: 2rem 1rem;
            text-align: center;
            &:nth-of-type(odd) .image-container{
                background-color: var(--clr-primary-300);
            }
            &:nth-of-type(even) .image-container{
                background-color: var(--clr-primary-600);
            }
            .image-container {
                margin: 1.5rem 0;
                padding: 4em;
                border-radius: 50%;
                overflow: hidden;
            }
        }
    }
}
    
</style>
