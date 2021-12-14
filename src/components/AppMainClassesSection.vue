<template>
    <section id="classes" class="container_small">
        <!-- section header -->
        <div class="section-title">
            <h2>Our Classes</h2>
            <span class="section-subtitle">Our preschool program has four dedicated classes</span>
            <img class="img-divider" src="../assets/img/header_divider.png" alt="styled divider">
        </div>
        <div class="plans-introduction">
            <div class=" intro introduction_title">
                <h3>We provided four classes with nine to twenty children each aged twelve month to nive years of age&period;</h3>
            </div>
            <div class="intro introduction_subtitle">
                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Natus molestias ad, ex vitae quos minima. Reiciendis vel illum earum numquam provident mollitia tempora, adipisci eius, ipsa deleniti nobis. Odit, officia.</p>
            </div>
        </div>
        <!-- section main -->
        <div class="cards">
            <div class="card" v-for="classCard, i in classesArr" :key="i">
                <div class="card_info">
                    <div class="main_info">
                        <h4>{{ classCard.title }}</h4>
                        <p>{{ classCard.subtitle }}</p>
                    </div>
                    <div class="age_class">
                        <p>{{ classCard.age }} <span>{{ classCard.ageText }}</span></p>
                        <p>{{ classCard.class }} <span> Class size </span></p>
                    </div>
                </div>
                <div class="card_image">
                    <img :src="classCard.image" alt="child class representation">
                    <button class="btn main-btn">
                        <a href="#">
                            read more <i class="fas fa-angle-right"></i>
                        </a>
                    </button>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppMainClassesSection',
    data() {
        return {
            classesArr: [
                {
                    title: "Little Lambs",
                    subtitle: "Class Name",
                    age: "12-24",
                    ageText: "Months old",
                    class: "9",
                    image: "./img/class_01-690x506.jpg"
                },
                {
                    title: "Bouncy Bears",
                    subtitle: "Class Name",
                    age: "2-3",
                    ageText: "Years old",
                    class: "12",
                    image: "./img/class_02-690x506.jpg"
                },
                {
                    title: "TenderHearts",
                    subtitle: "Class Name",
                    age: "3-4",
                    ageText: "Years old",
                    class: "15",
                    image: "./img/class_03-690x506.jpg"
                },
                {
                    title: "Shining Stars",
                    subtitle: "Class Name",
                    age: "4-5",
                    ageText: "Years old",
                    class: "20",
                    image: "./img/class_04-690x506.jpg"
                },
            ],
        }
    }
}
</script>

<style scoped lang="scss">
    #classes {
        margin: 2rem auto;
    }
    .section-title {
        text-align: center;
        h2 {
            font-weight: lighter;
        }
        span {
            color: var(--clr-secondary-200);
        }
    }
    .plans-introduction {
        display: flex;
        align-items: flex-start;
        .intro {
            width: 50%;
            padding: 2rem;
        }
        .introduction_title {
            h3 {
                margin: 0;
            }
        }
        .introduction_subtitle {
            p {
                color: var(--clr-secondary-400);
            }
        }
    }
    .cards {
        display: grid;
        gap: 1rem;
        grid-template-columns: repeat(2, 1fr);
        .card {
            background-color: var(--clr-primary-600);
            display: flex;
        }
        .card_info {
            display: flex;
            flex-flow: column nowrap;
            justify-content: space-between;
            width: 50%;
            padding: 1em;
            h4 {
                font-size: 1.5rem;
                font-weight: 400;
                color: var(--clr-primary-100);
            }
        }
        .age_class {
            text-align: center;
            display: flex;
            align-items: center;
            height: 30px;
            p {
                display: flex;
                flex-flow: column wrap;
                width: 50%;
                color: var(--clr-primary-100);
                &:first-child {
                    border-right: 1px solid var(--clr-secondary-400);
                }
                span {
                    color: var(--clr-secondary-200);
                    font-size: .8rem;
                }
            }
        }
        .card_image {
            margin: 0;
            width: 50%;
            position: relative;
            img {
                width: 100%;
                display: block;
            }
            button {
                position: absolute;
                bottom: 0;
                right: 0;
                i {
                    margin-left: 1rem;
                }
            }
        }
    }

</style>
