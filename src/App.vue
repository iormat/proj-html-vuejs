<template>
	<div id="app">
		<AppHeader
		:linksArr="navLinksArr"
		/>

		<AppMain/>
	</div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

export default {
	name: 'App',
	components: {
		AppHeader,
		AppMain,
	},
	data() {
		return {
			// array to simulate getting data from an API
			navLinksArr: [
				{
					title: "Home",
					selected: true,
					logo: "./img/home.png",
					logoHovered: "./img/home-2.png",
				},
				{
					title: "Pages",
					selected: false,
					logo: "./img/document.png",
					logoHovered: "./img/document-2.png",
				},
				{
					title: "Blog",
					selected: false,
					logo: "./img/printer.png",
					logoHovered: "./img/printer-2.png",
				},
				{
					title: "Shop",
					selected: false,
					logo: "./img/cart.png",
					logoHovered: "./img/cart-2.png",
				},
				{
					title: "Shortcodes",
					selected: false,
					logo: "./img/lab.png",
					logoHovered: "./img/lab-2.png",
				},
				{
					title: "Support",
					selected: false,
					logo: "./img/chat.png",
					logoHovered: "./img/chat-2.png",
				},
				{
					title: "Contact",
					selected: false,
					logo: "./img/envelope.png",
					logoHovered: "./img/envelope-2.png",
				},

			],
		}
	}
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap');

:root {
	--clr-primary-100: #fff;
	--clr-primary-300: #EC6F2D;
	--clr-primary-600: #55509A;
	--clr-primary-900: #000;

	--clr-secondary-200: #9E9E9E;
}
* {
	padding: 0;
	margin: 0;
	box-sizing: border-box;
}

#app {
	font-family: 'Roboto', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
}
// container rules
.container_small {
	max-width: 1000px;
	margin: 0 auto;
}
// image divider rules
.img-divider {
	display: block;
	margin: 1rem auto;
}

// text rules
h2 {
	color: var(--clr-primary-600);
	font-size: 3.2rem;
}

// btn rules
.btn {
	border: 0;
	& a {
		display: block;
		text-decoration: none;
		color: var(--clr-primary-100);
		text-transform: uppercase;
		font-size: 1rem;
		font-weight: bolder;
		padding: .8em;
	}
	&.banner-btn {
		background-color: var(--clr-primary-600);
		border: 2px solid var(--clr-primary-100);
		&:hover {
			background-color: var(--clr-primary-100);
			a {
				color: var(--clr-primary-600);
			}
		}
	}
	&.main-btn {
		background-color: var(--clr-primary-300);
		&:hover {
			background-color: var(--clr-primary-600);
		}
	}
}
</style>
