<template>
    <section id="strenghts">
        <div class="container_small">
            <!-- strenghts descriptions -->
            <div class="our_strenghts">
                <h2>We have been educating children for over fitfteen years. Our goal is to create a place that engages each child&period;</h2>
                <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quis molestias, incidunt deleniti maxime, harum reiciendis iste sed aspernatur alias ad laboriosam dolor tempora deserunt quas aliquid obcaecati mollitia sequi maiores.</p>
                <ul>
                    <li><i class="far fa-check-square"></i>Lorem ipsum dolor sit amet consectetur, adipisicing elit.</li>
                    <li><i class="far fa-check-square"></i>Pariatur, quia molestias ad voluptate a hic tempore!</li>
                    <li><i class="far fa-check-square"></i>Aliquid ratione nulla sit repellat eveniet, eos officia?</li>
                    <li><i class="far fa-check-square"></i>Tenetur est assumenda odio, sed ratione maiores dicta.</li>
                    <li><i class="far fa-check-square"></i>Omnis accusamus repellat eaque, obcaecati impedit facere.</li>
                    <li><i class="far fa-check-square"></i>Quis, cupiditate laboriosam accusantium sint sapiente saepe!</li>
                </ul>
            </div>
            <!-- company policy and priorities -->
            <div class="priorities">
                <div class="card" v-for="card, i in cardsArr" :key="i">
                    <div class="image_container">
                        <img loading="lazy" :src="card.image" :alt="card.title">
                    </div>
                    <div class="text_container">
                        <h3> {{card.title}} </h3>
                        <p> {{card.definition}} </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppMainStrenghtsSection',
    data() {
        return {
            cardsArr: [
                {
                    image: "./img/toy.png",
                    title: "Learning & Fun",
                    definition: "Lorem ipsum dolor sit amet consectetur adipisicing."
                },
                {
                    image: "./img/meal.png",
                    title: "Healthy Meals",
                    definition: "Lorem ipsum dolor sit amet consectetur adipisicing."
                },
                {
                    image: "./img/school.png",
                    title: "Friendly Place",
                    definition: "Lorem ipsum dolor sit amet consectetur adipisicing."
                },
                {
                    image: "./img/shield.png",
                    title: "Children Safety",
                    definition: "Lorem ipsum dolor sit amet consectetur adipisicing."
                },
            ]
        }
    }
}
</script>

<style scoped lang="scss">
    #strenghts {
        background-color: var(--clr-primary-200);
        padding: 2rem auto;
        .container_small {
            display: flex;
            padding: 4rem 0;
            & > * {
                width: 50%;
                padding: 1em;
            }
            .our_strenghts {
                h2 {
                    font-size: 1.7rem;
                    margin-bottom: 2rem;
                }
                p {
                    color: var(--clr-secondary-400);
                    font-size: 1rem;
                    margin-bottom: 1rem;
                }
                ul {
                    display: flex;
                    flex-flow: column wrap;
                    justify-content: center;
                }
                li {
                    color: var(--clr-secondary-400);
                    list-style: none;
                    margin: .2rem 0;
                    i {
                        margin-right: .25rem;
                        color: var(--clr-primary-300);
                    }
                }
            }
            .priorities {
                display: grid;
                grid-template-columns: repeat(2, 1fr);
                text-align: center;
                gap: 1.5rem;
                .image_container {
                    display: inline-block;
                    background-color: var(--clr-primary-100);
                    border-radius: 50%;
                    img {
                        display: block;
                        height: 30px;
                        width: 30px;
                        margin: 1.8em;
                    }
                }
                p {
                    color: var(--clr-secondary-400);
                }
            }
        }
    }

</style>