<template>
    <section id="overview">
        <div class="container_small">
            <!-- left side -->
            <div class="side overview-sx">
                <nav class="overview_nav">
                    <h2>Overview</h2>
                    <h2>Our Mission</h2>
                    <div class="triangle-down"></div>
                </nav>

                <div class="contextual-info">
                    <!-- first info -->
                    <h3>Our philosophy is learning through play as we offer a stimulating environment for children</h3>
                    <div class="flex-container">
                        <div class="image_container">
                            <img src="../assets/img/clock_alt.png" alt="clock image">
                        </div>
                        <div class="text">
                            <h4>Full day Session</h4>
                            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vero, soluta ea suscipit quos eos cumque!</p>
                        </div>
                    </div>
                    <!-- second info -->
                    <div class="flex-container">
                        <div class="image_container">
                            <img src="../assets/img/clock_alt.png" alt="clock image">
                        </div>
                        <div class="text">
                            <h4>Full day Session</h4>
                            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vero, soluta ea suscipit quos eos cumque!</p>
                        </div>
                    </div>
                </div>
            </div>
            <!-- right side -->
            <div class="side overview-dx">
                <div class="slider">
                    <img :src="sliderArr[activePos].sliderImage" alt="">
                    <div class="arrow prev" @click="prevImg"><i class="fas fa-angle-left"></i></div>
                    <div class="arrow next" @click="nextImg"><i class="fas fa-angle-right"></i></div>
                </div>
                <div class="thumb-container">
                    <div class="thumbs" v-for="slide, i in sliderArr" :key="i" @click="checkPosition(sliderArr, i)">
                        <img :class="slide.selected ? 'active' : '' " :src="slide.thumbImage" alt="teaching environment">
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppMainOverviewSection',
    data() {
        return {
            activePos: 0,
            sliderArr: [
                {
                    sliderImage: "./img/gallery_08-690x506.jpg",
                    thumbImage: "./img/gallery_08-690x506.jpg",
                    selected: true,
                },
                {
                    sliderImage: "./img/gallery_01.jpg",
                    thumbImage: "./img/gallery_01.jpg",
                    selected: false,
                },
                {
                    sliderImage: "./img/gallery_07-690x506.jpg",
                    thumbImage: "./img/gallery_07-690x506.jpg",
                    selected: false,
                }
            ]
        }
    },
    methods: {
		// get current selection
		checkPosition(sliderArr, i) {
			if(this.activePos !== i){
				sliderArr.forEach(element => {
					element.selected = false
				});
				this.activePos = i;
				sliderArr[this.activePos].selected = true
			}
		},
        // function to go to the next image
        nextImg: function() {
            if(this.activePos < this.sliderArr.length - 1){
                this.sliderArr.forEach(element => {
					element.selected = false
				});
                this.activePos++;
                this.sliderArr[this.activePos].selected = true
            }else {
                this.sliderArr.forEach(element => {
					element.selected = false
				});
                this.activePos = 0;
                this.sliderArr[this.activePos].selected = true
            }
        },
        // function to go to the previous image
        prevImg: function() {
            if(this.activePos === 0){
                this.sliderArr.forEach(element => {
					element.selected = false
				});
                this.activePos = this.sliderArr.length - 1;
                this.sliderArr[this.activePos].selected = true
            }else {
                this.sliderArr.forEach(element => {
					element.selected = false
				});
                this.activePos --;
                this.sliderArr[this.activePos].selected = true
            }
        },       
	},
}
</script>

<style scoped lang="scss">
    #overview {
        background-color: var(--clr-primary-200);
        padding: 2rem 0;
        .container_small {
            margin: 2rem auto;
            display: flex;
            flex-flow: row wrap;
            justify-content: space-between;
        }
        .side {
            width: 48%;
        }
        // left side
        .overview-sx {
            .overview_nav {
                position: relative;
            }
            h2 {
                font-size: 1rem;
                display: inline-block;
                padding: 1em 2em;
                color: var(--clr-secondary-200);
                border-bottom: 1px solid var(--clr-secondary-200);
                &:first-child {
                    position: relative;
                    z-index: 1;
                    border: 0;
                    margin-right: 1rem;
                    background-color: var(--clr-primary-300);
                    color: var(--clr-primary-100);
                }
            }

            .triangle-down {
                position: absolute;
                background-color: var(--clr-primary-300);
                height: 30px;
                width: 30px;
                transform: rotate(45deg);
                bottom: 0px;
                left: 10%;
                z-index: 0;
            }

            h3 {
                margin: 2rem 0;
                font-size: 2rem;
                font-weight: 400;
            }
            .contextual-info {
                .flex-container {
                    display: flex;
                    flex-flow: row nowrap;
                    margin: 2rem 0;
                }
                .image_container {
                    background-color: var(--clr-primary-300);
                    border-radius: 50%;
                    padding: 2rem;
                    img {
                        display: block;
                        width: 30px;
                        aspect-ratio: 1;
                    }
                }
                .text {
                    margin-left: 1rem;
                    h4 {
                        font-size: 1.5rem;
                        font-weight: 400;
                        margin-bottom: 1.2rem;
                    }
                }
            }
        }
        // right side
        .overview-dx {
            .slider {
                position: relative;

                img {
                    width: 100%;
                    display: block;
                }
                .arrow {
                    cursor: pointer;
                    position: absolute;
                    top: 50%;
                    color: var(--clr-primary-100);
                    background-color: var(--clr-primary-300);
                    width: 40px;
                    height: 40px;
                    text-align: center;
                    line-height: 30px;
                    padding: .3em;
                    transform: translateY(-50%);
                    &.prev {
                        left: 0;
                    }
                    &.next {
                        right: 0;
                    }
                }
            }
            .thumb-container {
                margin-top: .75rem;
                display: grid;
                grid-template-columns: repeat(3, 1fr);
                gap: .75rem;
                img {
                    padding-bottom: .25rem;
                    cursor: pointer;
                    display: block;
                    width: 100%;
                    filter: opacity(.5);
                    &.active {
                        filter: opacity(1);
                        border-bottom: 2px solid var(--clr-primary-300);
                    }
                }
            }
        }
    }
</style>