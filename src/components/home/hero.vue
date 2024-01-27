<template>
	<div class="hero-wrapper">
		<div class="row justify-center full-height items-center">
			<div class="col-12">
				<div class="row justify-center">
					<div class="col-12 col-md-9 text-center">
						<div class="tree-wrapper">
							<img class="tree" src="src/assets/tree.png" alt />
							<img class="falling-leaf one" src="src/assets/leaf.png" />
							<img class="falling-leaf two" src="src/assets/leaf.png" />
							<img class="falling-leaf three" src="src/assets/leaf.png" />
							<img class="falling-leaf four" src="src/assets/leaf.png" />
							<img class="falling-leaf five" src="src/assets/leaf.png" />
							<img class="falling-leaf six" src="src/assets/leaf.png" />
						</div>
					</div>
					<div class="col-12 col-md-9 text-white text-center">
						<p class="text-h2" id="heroTitle">HHC Next</p>
						<p class="text-h4" id="heroText">A holistic approach to health care</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'components-home-hero',
	setup () {
		return {}
	}
}
</script>


<style lang="scss" scoped>
.hero-wrapper {
	position: relative;
	height: 100vh;
	background: linear-gradient(
			rgba(34, 34, 34, 0.875),
			rgba(34, 34, 34, 0.875)
		),
		url("src/assets/forest3.jpg");
	background-attachment: fixed;
	background-size: cover;
	background-position: top;
	background-repeat: no-repeat;
	h1 {
		font-weight: 300;
		letter-spacing: 3px;
		color: rgba(256, 256, 256, 0.9);
		font-size: 3.5rem;
		line-height: 1;
	}

	.tree-wrapper {
		text-align: center;
		position: relative;
		display: inline-block;

		img.tree {
			height: 300px;
		}
		img.falling-leaf {
			height: 20px;
			position: absolute;
		}
		.one {
			top: 125px;
			left: 125px;
			animation: 3s falling infinite 0s;
		}
		.two {
			top: 75px;
			left: 67px;
			animation: 3s falling infinite 0.5s;
		}
		.three {
			top: 175px;
			left: 75px;
			animation: 3s falling infinite 1s;
		}
		.four {
			top: 168px;
			left: 218px;
			animation: 3s falling infinite 1.5s;
		}
		.five {
			top: 75px;
			left: 220px;
			animation: 3s falling infinite 2s;
		}
		.six {
			top: 50px;
			left: 180px;
			animation: 3s falling infinite 2.5s;
		}
	}
}
.bar {
	height: 5vh;
	background-color: #222;
}
.hero-image {
	height: 90vh;
	background: linear-gradient(rgba(34, 34, 34, 0.75), rgba(34, 34, 34, 0.75)),
		url("../assets/forest3.jpg");
	background-size: cover;
}
.down {
	position: absolute;
	bottom: 7.5vh;
	left: calc(50vw - 10px);
	color: #222;
	animation: 1500ms slide infinite ease;
}

@keyframes falling {
	0% {
		-webkit-transform: translate3d(0, 0, 0) rotate(0deg);
		opacity: 1;
	}

	100% {
		-webkit-transform: translate3d(-65px, 125px, 0) rotate(360deg);
		opacity: 0.1;
	}
}
</style>