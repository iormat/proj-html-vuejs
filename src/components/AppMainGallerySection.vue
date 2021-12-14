<template>
    <section id="gallery">
        <div class="gallery_photos">
            <div class="photo" v-for="photo, i in photosArr" :key="i">
                <img :src="photo.image" alt="published children photos">
                <div class="add_photo">
                    <img src="../assets/img/image_overlay.png" alt="add new photo">
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
                    width: 3rem;
                    height: 3rem;
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


</style>