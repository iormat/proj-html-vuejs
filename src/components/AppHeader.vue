<template>
	<header>
		<nav class="header-nav">
			<div class="container_small">
				<!-- main page logo -->
				<a href="#">
					<img src="../assets/img/logo.png" alt="fable logo">
				</a>
				<!-- list of header links -->
				<ul>
					<li :class="link.selected ? 'selected' : '' " @click="checkPosition(linksArr, i)" v-for="link, i in linksArr" :key="i">
						<a href="#">
							<img class="base_img" :src="link.logo" :alt="link.title">
							<img class="hovered_img" :src="link.logoHovered" :alt="link.title">
							<h4>{{ link.title }}</h4>
						</a>
					</li>
				</ul>
			</div>
		</nav>
		<!-- jumbo section -->
		<section class="jumbotron">
			<div class="container_small">
				<div class="left_side">
					<span class="friendly_txt">Friendly Atmosphere</span>
					<h2>Welcoming Place</h2>
					<span class="subtitle">For Every Child</span>
					<button class="btn main-btn">
						<a href="#">buy this theme now</a>
					</button>
				</div>

				<div class="right_side">
					<!-- decorative immages -->
					<div class="jumbo_background">
						<img src="../assets/img/slider_icon11.png" alt="decorative playful background images">
						<img src="../assets/img/slider_icon12.png" alt="decorative playful background images">
						<img src="../assets/img/slider_icon14.png" alt="decorative playful background images">
						<img src="../assets/img/slider_icon16.png" alt="decorative playful background images">
						<img src="../assets/img/slider_icon13.png" alt="decorative playful background images">
						<!-- background child -->
						<img src="../assets/img/slider_slide2_img2.png" alt="playing child">
					</div>
					<!-- foreground child image -->
					<div class="jumbo_foreground">
						<img src="../assets/img/slider_slide2_img1.png" alt="playing child">
					</div>
				</div>
				<!-- bottom rectangles -->
				<div class="bottom_section">
					<div class="small_rectangle"></div>
					<div class="small_rectangle"></div>
					<div class="small_rectangle"></div>
				</div>
			</div>
		</section>
		<!-- enroll your child -->
		<section class="enroll">
			<div class="container_small">
				<h3>How to Enroll Your Child to a Class&quest;</h3>
				<button class="btn banner-btn">
					<a href="#">
						view gallery
						<i class="fas fa-angle-right"></i>	
					</a>
				</button>
			</div>
		</section>
	</header>
</template>

<script>
export default {
	name: 'AppHeader',
	props: {
		linksArr: Array,
	},
	data() {
		return {
			activePos: 0,
		}
	},
	methods: {
		// get current selection
		checkPosition(linksArr, i) {
			if(this.activePos !== i){
				linksArr.forEach(element => {
					element.selected = false
				});
				this.activePos = i;
				linksArr[this.activePos].selected = true
				console.log(this.activePos);
			}
		}
	},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Handlee&family=Roboto:wght@400;700&display=swap');

	header {
		& img {
			height: 100px;
			display: block;
		}
	}

	.header-nav {
		background-color: var(--clr-primary-100);
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		z-index: 7;
	}

	.header-nav .container_small {
		display: flex;
		justify-content: space-between;
	}

	.header-nav ul {
		margin: 0;
		font-size: .8rem;
		padding: 0;
		list-style: none;
		display: grid;
		grid-template-columns: repeat(7, 1fr);
		text-align: center;
		gap: 0 .5rem;
	}

	.header-nav li {
		height: 100%;
		&:hover {
			background-color: var(--clr-primary-300);
		}
		&:hover a {
			color: var(--clr-primary-100);
		}
		&:hover .base_img {
			display: none;
		}
		&:hover .hovered_img {
			display: block;
		}

		& a {
			padding: 1em .5em;
			display: grid;
			height: 100%;
			width: 100%;
			color: var(--clr-primary-600);
			text-decoration: none;
		}

		& img {
			margin: auto;
			width: 30px;
			height: auto;
			margin-bottom: .5rem;
		}

		& .hovered_img {
			display: none;
		}
		// selected styling
		&.selected {
				background-color: var(--clr-primary-300);
			& a {
				color: var(--clr-primary-100);
			}
			& .base_img {
				display: none;
			}
			& .hovered_img {
				display: block;
			}
		}
	}
	// JUOMBOTRON
	.jumbotron {
		position: relative;
		height: 600px;
		margin-top: 100px;
		background-image: url('../assets/img/slider_slide2_background.png');
		background-size: contain;
		// LEFT_SIDE
		.left_side {
			width: 40%;
			padding-top: 150px;
			.friendly_txt {
				color: var(--clr-primary-300);
				font-family: 'Handlee', 'Roboto', sans-serif;
				font-size: 2.5rem;
			}
			h2 {
				color: var(--clr-primary-600);
				font-size: 3.2rem;
			}
			.subtitle {
				color: var(--clr-primary-600);
				font-size: 3rem;
				font-weight: 300;
			}
			.btn.main-btn {
				margin-top: 1.2rem;
			}
		}
		// RIGHT_SIDE
		// jumbotron background images
		.jumbo_background img {
			position: absolute;
			width: 70px;
			height: auto;
		}
		// jumbo background small images
		.jumbo_background img{
			z-index: 1;
			// brush
			&:nth-child(1) {
				top: 5%;
				left: 40%
			}
			// train
			&:nth-child(2) {
				top: 20%;
				left: 46%
			}
			// circle
			&:nth-child(3) {
				top: 20%;
				left: 35%
			}
			// alphabet
			&:nth-child(4) {
				top: 5%;
				left: 28%
			}
			// lab
			&:nth-child(5) {
				top: 5%;
				left: 51%
			}
			// child
			&:last-child {
				width: 28%;
				right: 8%;
				top: 8%;
			}
		}
		// jumbo foreground image
		.jumbo_foreground img {
			z-index: 2;
			position: absolute;
			width: 32%;
			height: auto;
			left: 42%;
			top: 0;
		}
		// BOTTOM_SECTION
		.bottom_section {
			margin-top: 150px;
			width: 100%;
			display: flex;
			justify-content: center;			
			.small_rectangle {
				margin: .5rem;
				width: 60px;
				height: 20px;
				border: 2px solid var(--clr-primary-300);
				&:nth-child(2) {
					position: relative;
					bottom: 20px;
				}
			}
		}
	}
	//ENROLL SECTION
	.enroll {
		padding: 2em 0;
		background-color: var(--clr-primary-600);
		color: var(--clr-primary-100);
		& .container_small {
			display: flex;
			justify-content: space-between;
			align-items: center;
		}
		h3 {
			font-size: 2rem;
			font-weight: 300;
		}
		.btn.banner-btn {
			font-weight: 700;
			& a i {
				margin-left: .5rem;
			}
		}
	}
</style>