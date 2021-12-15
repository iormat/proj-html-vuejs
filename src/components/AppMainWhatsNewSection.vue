<template>
    <section id="whats_new" class="container_small">
        <!-- section header -->
        <div class="section-title">
            <h2>What&apos;s New</h2>
            <span class="section-subtitle">Keep up to date with the latest news</span>
            <img loading="lazy" class="img-divider" src="../assets/img/header_divider.png" alt="styled divider">
        </div>
            <!-- articles -->
            <div class="articles">
            <article v-for="article, i in articlesArr" :key="i">
                <time> {{article.date}} </time>
                <div class="image-container">
                    <img loading="lazy" :src="article.image" :alt="article.title">
                    <span class="counter"> {{ article.counter }} </span>
                </div>
                <h3> {{article.title}} </h3>
                <p> {{article.text}} </p>
                <hr>
                <!-- article footer -->
                <footer>
                    <span class="publisher"> 
                        <img loading="lazy" src="../assets/img/author.png" :alt="article.publisher">
                        {{article.publisher}} 
                    </span>
                    <span class="actvity-genre">
                        <img loading="lazy" src="../assets/img/category.png" :alt="article.activityGenre"> 
                        {{article.activityGenre}} 
                    </span>
                </footer>
            </article>
        </div>
        <div class="section-btn">
            <button class="btn main-btn"> 
                <a href="#"> go to blog <i class="fas fa-angle-right"></i></a>
            </button>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppMainWhatsNewSection',
    data() {
        return {
            articlesArr: [
                {
                    date: "October, 3, 2014",
                    image: "./img/blog_09-300x180.jpg",
                    title: "Drawing and Painting Lessons",
                    text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus similique praesentium doloribus iure doloremque, consequatur voluptatum optio mollitia temporibus ex.",
                    publisher: "Anna Brown",
                    activityGenre: "Events, Fun",
                    counter: "42"
                },
                {
                    date: "October, 3, 2014",
                    image: "./img/blog_10-300x180.jpg",
                    title: "Fall Parents Meeting Day",
                    text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus similique praesentium doloribus iure doloremque, consequatur voluptatum optio mollitia temporibus ex.",
                    publisher: "Anna Brown",
                    activityGenre: "Dance, Education",
                    counter: "19"
                },
                {
                    date: "September, 20, 2014",
                    image: "./img/blog_08-300x180.jpg",
                    title: "Birthday in Kindergarten",
                    text: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus similique praesentium doloribus iure doloremque, consequatur voluptatum optio mollitia temporibus ex.",
                    publisher: "Anna Brown",
                    activityGenre: "Games, General",
                    counter: "22"
                },
            ],
        }
    }
}
</script>

<style scoped lang="scss">
    #whats_new {
        text-align: center;
        margin: 2rem auto;
        // section header styles
        h2 {
            font-weight: lighter;
        }
        // article styles
        .articles {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1.5rem;
            text-align: left;
            time, span {
                color: var(--clr-secondary-200);
            }
            .image-container {
                position: relative;
                img {
                    width: 100%;
                    display: block;
                    margin-top: 1rem;
                }
            }
            .counter {
                position: absolute;
                bottom: 0;
                right: 0;
                background-color: var(--clr-primary-300);
                color: var(--clr-primary-100);
                padding: 1em;
                font-size: .8rem;
            }
            hr {
                margin: .75rem 0;
                color: var(--clr-primary-200);
            }
            footer {
                display: flex;
                justify-content: space-between;
                align-items: center;
                span {
                    width: 48%;
                    display: flex;
                    flex-wrap: nowrap;
                    align-items: center;
                    img {
                        margin: 0 .4rem 0 0;
                        width: 10%;
                    }
                }
            }
        }
        // button
        .section-btn {
            text-align: center;
            margin: 2rem 0;
            i {
                margin-left: .5rem;
            }
        }
    }
</style>