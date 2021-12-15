<template>
    <section id="gallery">
        <div class="gallery_photos">
            <div class="photo" v-for="photo, i in photosArr" :key="i">
                <img loading="lazy" :src="photo.image" alt="published children photos">
                <div class="add_photo">
                    <img loading="lazy" src="../assets/img/image_overlay.png" alt="add new photo">
                </div>
            </div>
        </div>
        <div class="photo_banner">
            <div class="container_small">
				<h2>See Our Kindergarten Photo Gallery&excl;</h2>
				<button class="btn banner-btn">
					<a href="#">
						view gallery
						<i class="fas fa-angle-right"></i>	
					</a>
				</button>
			</div>
        </div>
        <!-- jumbotron -->
        <div class="jumbotron">
            <div class="container_small">
                <div>
                    <img src="../assets/img/quote_alt.png" alt="quotes">
                </div>
                <h2>I have to say that I have 2 children ages 5 and 2 and have used various daycare's in Kindergartens and this is by far the very best I have ever used.</h2>
                <span class="underline"></span>
                <span class="sign">Cecil J&period; Kirk</span>
                <!-- empty divs to make rectangles -->
                <div class="rectangle"></div>
                <div class="rectangle"></div>
                <div class="rectangle"></div>
                <div class="rectangle"></div>
                <div class="rectangle"></div>
                <div class="rectangle"></div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppMainGallerySection',
    data() {
        return {
            photosArr: [
                {
                    image: "./img/gallery_01-690x506.jpg",
                },
                {
                    image: "./img/gallery_02-690x506.jpg",
                },
                {
                    image: "./img/gallery_03-690x506.jpg",
                },
                {
                    image: "./img/gallery_04-690x506.jpg",
                },
            ]
        }
    }
}
</script>

<style scoped lang="scss">
    .gallery_photos {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        .photo {
            position: relative;
            cursor: pointer;
            .add_photo {
                display: none;
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
                display: block;
            }
        }
        img {
            width: 100%;
            display: block;
        }
    }
    .photo_banner {
        padding: 2rem 0;
        background-image: url('../assets/img/pattern.png');
        .container_small {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        h2 {
            color: var(--clr-primary-100);
            font-size: 2rem;
            font-weight: 400;
        }
    }
    .jumbotron {
        padding: 2rem;
        background-image: url('../assets/img/parallax_02.jpg');
        background-size: cover;
        background-position: center;
        .container_small {
            text-align: center;
            & div:first-child {
                display: inline-block;
                border-radius: 50%;
                border: 2px solid var(--clr-primary-100);
                padding: 2rem;
            }
            img {
                display: block;
                width: 3rem;
                height: 3rem;
            }
            h2 {
                color: var(--clr-primary-100);
                font-size: 2.18rem;
                font-weight: 300;
                margin: 2rem 0 0 0;
            }
            .underline {
                display: inline-block;
                margin: 2.5rem;
                border: 1px solid var(--clr-primary-100);
                width: 10ch;
            }
            .sign {
                display: block;
                color: var(--clr-primary-100);
            }
            .rectangle {
                display: inline-block;
                height: .75rem;
                width: 2.3rem;
                border: 1px solid var(--clr-primary-100);
                margin: 2rem .25rem;
                &:nth-of-type(4) {
                    position: relative;
                    bottom: .7rem;
                }
            }
        }
    }
</style>