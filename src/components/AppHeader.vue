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
					<li @click.prevent="checkPosition(linksArr, i)" v-for="link, i in linksArr" :key="i">
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
					<button>
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
		checkPosition(linksArr, i) {
			if(this.activePos !== i){
				this.activePos = i;
				linksArr[this.activePos].selected = true
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

	.container_small {
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
			display: inline-block;
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
			width: 50%;
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
			button {
				display: block;
				margin-top: 1.2rem;
				padding: .8em;
				border: 0;
				background-color: var(--clr-primary-300);
				& a {
					text-decoration: none;
					color: var(--clr-primary-100);
					text-transform: uppercase;
					font-size: 1rem;
					padding: .8em;
				}
			}
		}
		// RIGHT_SIDE
		// jumbotron background images
		.jumbo_background img {
			position: absolute;
			width: 70px;
			height: auto;
		}
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
		}
	}
</style>
