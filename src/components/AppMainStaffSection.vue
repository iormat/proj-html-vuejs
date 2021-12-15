<template>
    <section id="staff" class="container_small">
        <!-- section header -->
        <div class="section-title">
            <h2>Meet Our Staff</h2>
            <span class="section-subtitle">With education and experience in early childhood care</span>
            <img loading="lazy" class="img-divider" src="../assets/img/header_divider.png" alt="styled divider">
        </div>
        <!-- section staff introduction -->
        <div class="staff-introduction">
            <div class=" intro introduction_title">
                <h3>Our staff consists of three teachers and one assistant with experience in early childhood care&period;</h3>
            </div>
            <div class="intro introduction_subtitle">
                <p>Praesent arcu gravida vehicula est node maecenas loareet morbi a dosis luctus. Urna eget lacinia eleifend praesent luctus a arcu quis facilisis venenatis. Aenean interdum, nibh vitae sodales, magna ante feugiat elit maecenas.</p>
            </div>
        </div>
        <!-- cards -->
        <div class="staff-cards">
            <div class="card" v-for="staff, i in staffArr" :key="i">
                <div class="staff">
                    <div class="image-container">
                        <img loading="lazy" class="staff-image" :src="staff.image" :alt="staff.name">
                        <div class="add_photo">
                            <img loading="lazy" src="../assets/img/image_overlay.png" alt="add new photo">
                        </div>
                    </div>
                    <div class="staff-info">
                        <h4> {{ staff.name }} </h4>
                        <span> {{ staff.role }} </span>
                    </div>
                </div>

                <div class="description">
                    <div class="quote-container">
                        <img loading="lazy" src="../assets/img/quote.png" alt="quotes">
                    </div>
                    <p>{{ staff.description }}</p>
                    <span class="social">
                        <a href="#"><img :src="staff.social1" alt="social logo"></a>
                        <a href="#"><img :src="staff.social2" alt="social logo"></a>
                        <a href="#"><img :src="staff.social3" alt="social logo"></a>
                    </span>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppMainStaffSection',
    data() {
        return {
            staffArr: [
                {
                    name: "Ruth Richie",
                    role: "Teacher",
                    description: "I have just finished my studies in Early Childhood Education, and I am also the kid’s yoga teacher here at Fable. I enjoy cooking, swimming and bike riding in my free time.",
                    image: "./img/team_01.jpg",
                    social1: "./img/mail.png",
                    social2: "./img/facebook.png",
                    social3: "./img/pinterest.png",
                },
                {
                    name: "Katie Willmore",
                    role: "Assistant Teacher",
                    description: "My name is Katie. I grew up and studied in Canada. This is my second year at Fable and love every minute of it, making the children’s learning experience fun.",
                    image: "./img/team_02.jpg",
                    social1: "./img/dribbble.png",
                    social2: "./img/stumbleupon.png",
                    social3: "./img/instagram.png",
                },
                {
                    name: "Angelica Watson",
                    role: "Teacher",
                    description: "I hold a degree in Early Childhood Education and an advanced English language certificate. I have been working as a kindergarten teacher since 2002.",
                    image: "./img/team_03.jpg",
                    social1: "./img/bing.png",
                    social2: "./img/skype.png",
                    social3: "./img/linkedin.png",
                },
                {
                    name: "Angela Lynn",
                    role: "Teacher",
                    description: " have completed a Graduate Diploma in Early Childhood Teaching. I have worked with children aged from six weeks to eight years. This is my second year at Fable.",
                    image: "./img/team_04.jpg",
                    social1: ".img/youtube.png",
                    social2: "./img/twitter.png",
                    social3: "./img/googleplus.png",
                },
            ],
        }
    }
}
</script>

<style lang="scss" scoped>
    #staff {
        // title section
        .section-title {
            margin: 2rem auto;
            text-align: center;
            h2 {
                font-weight: lighter;
            }
            span {
                color: var(--clr-secondary-200);
            }
        }
        .staff-introduction {
            display: flex;
            align-items: flex-start;
            .intro {
                width: 50%;
                padding: 2rem;
            }
            .introduction_title {
                h3 {
                    margin: 0;
                    font-size: 1.5rem;
                }
            }
            .introduction_subtitle {
                p {
                    color: var(--clr-secondary-400);
                }
            }
        }

        // card section
        .staff-cards {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            .card {
                margin: 2rem 0;
                display: flex;
                .image-container {
                    position: relative;
                }
                img {
                    width: 100%;
                    display: block;
                }
            }
        }
        .staff, .description {
            width: 50%;
        }

        .staff {
            overflow-x: hidden;
            span {
                display: block;
            }
            h4, span {
                text-align: center;
                margin: .25rem 0;
            }
            .staff-image {
                position: relative;
                bottom: 0;
                transition: linear .2s;
            }
            // hover effects
            .add_photo {
                opacity: 0;
                transition: linear .2s;
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                background-color: #55509aab;
                padding: 2em;
                border-radius: 50%;
                img {
                    width: 2.5rem;
                    height: 2.5rem;
                }
            }           
            &:hover .add_photo {
                opacity: 1;
                transition: linear .2s;
            }

            &:hover {
                cursor: pointer;
                background-color: rgba(75, 75, 75, 0.055);
            }
            &:hover .staff-image, &:hover .staff-info {
                transition: linear .2s;
                bottom: 20px;
            }
        }
        .staff-info {
            margin-top: 2rem;
            position: relative;
            bottom: 0;
            transition: linear .2s;
        }
        .description {
            display: flex;
            flex-flow: column nowrap;
            justify-content: space-between;
            padding: 1rem;
            .quote-container {
                width: 15ch;
                display: flex;
                justify-content: flex-end;
                padding: .2em .5em;
                border: 2px solid var(--clr-primary-300);
                position: relative;
                right: 25%;
                & img {
                    width: 5ch;
                }
            }
            p {
                font-size: 1.2rem;
            }
            .social {
                display: flex;
                a {
                    padding: 0;
                    margin:0 .1rem;
                    background-color: var(--clr-primary-300);
                }
            }
        }

    }

</style>