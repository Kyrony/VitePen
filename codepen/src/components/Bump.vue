<script>


export default {
	data() {
		return {
			Bump: false,
			Fire: false,
		}
	},
	methods: {
		fistBump() {
			this.Bump = true;
			setTimeout(() => {
				this.Bump = false;
			}, 3000);
		},
		fireFist() {
			this.Fire = true;
			const tween = KUTE.fromTo(
				'#fire1',
				{ path: '#fire1' },
				{ path: '#fire2' },
				{ repeat: 100, duration: 400, }
			)
			tween.start();
			const tween2 = KUTE.fromTo(
				'#fire3',
				{ path: '#fire3' },
				{ path: '#fire4' },
				{ repeat: 100, duration: 400, }
			)
			tween2.start();
			this.fistBump();
			setTimeout(() => {
				this.Fire = false;
			}, 4000);
		},
	},
}

</script>


<template>
	<div class="fistbump">
		<div class="bump-options">
			<button @click="fistBump()">Basic Bump</button>
			<button @click="fireFist()">Electric Bump</button>
		</div>
		<span :class="{ 'left-bump': Bump, 'left-fire': Fire }" class="left-fist">🤜
			<svg v-show="Fire" id="visual" viewBox="0 0 900 600" width="400" height="400" xmlns="http://www.w3.org/2000/svg"
				xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1">
				<g transform="translate(502.0613822257984 309.2608498199237)">
					<path id="fire1"
						d="M135.4 -194.4C153.2 -173.4 130.1 -104.1 120.9 -57.1C111.6 -10.1 116.2 14.6 121.4 52.1C126.6 89.5 132.3 139.8 112.2 154.3C92.1 168.7 46 147.4 -4.2 153.2C-54.5 159 -108.9 191.9 -142.4 181.8C-175.8 171.7 -188.3 118.4 -207.8 65.8C-227.3 13.1 -253.9 -39 -243.9 -82.1C-233.9 -125.2 -187.2 -159.3 -140.4 -170.9C-93.7 -182.6 -46.8 -171.8 6 -180C58.8 -188.2 117.6 -215.5 135.4 -194.4"
						fill="none" stroke="#84f4fff5" stroke-width="8"></path>
				</g>
				<g transform="translate(453.5480853425221 294.6294137367854)" style="visibility: hidden">
					<path id="fire2"
						d="M83.3 -119C101.1 -101.7 104.1 -68.2 135.2 -30.2C166.4 7.7 225.9 50.2 237 95.9C248.2 141.6 211.1 190.5 163.5 195.8C116 201 58 162.5 0.1 162.4C-57.8 162.2 -115.6 200.4 -146.5 189.8C-177.4 179.2 -181.4 119.7 -199.6 64.7C-217.8 9.6 -250.1 -41.1 -245.7 -87.5C-241.2 -134 -200 -176.2 -152.9 -184.1C-105.8 -192 -52.9 -165.5 -10.1 -151.6C32.7 -137.7 65.4 -136.4 83.3 -119"
						fill="none" stroke="#84f4fff5" stroke-width="8"></path>
				</g>
			</svg>
		</span>
		<span :class="{ 'right-bump': Bump, 'right-fire': Fire }" class="right-fist">🤛
			<svg v-show="Fire" id="visual" viewBox="0 0 900 600" width="400" height="400" xmlns="http://www.w3.org/2000/svg"
				xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1">
				<g transform="translate(502.0613822257984 309.2608498199237)">
					<path id="fire3"
						d="M135.4 -194.4C153.2 -173.4 130.1 -104.1 120.9 -57.1C111.6 -10.1 116.2 14.6 121.4 52.1C126.6 89.5 132.3 139.8 112.2 154.3C92.1 168.7 46 147.4 -4.2 153.2C-54.5 159 -108.9 191.9 -142.4 181.8C-175.8 171.7 -188.3 118.4 -207.8 65.8C-227.3 13.1 -253.9 -39 -243.9 -82.1C-233.9 -125.2 -187.2 -159.3 -140.4 -170.9C-93.7 -182.6 -46.8 -171.8 6 -180C58.8 -188.2 117.6 -215.5 135.4 -194.4"
						fill="none" stroke="#84f4fff5" stroke-width="8"></path>
				</g>
				<g transform="translate(453.5480853425221 294.6294137367854)" style="visibility: hidden">
					<path id="fire4"
						d="M83.3 -119C101.1 -101.7 104.1 -68.2 135.2 -30.2C166.4 7.7 225.9 50.2 237 95.9C248.2 141.6 211.1 190.5 163.5 195.8C116 201 58 162.5 0.1 162.4C-57.8 162.2 -115.6 200.4 -146.5 189.8C-177.4 179.2 -181.4 119.7 -199.6 64.7C-217.8 9.6 -250.1 -41.1 -245.7 -87.5C-241.2 -134 -200 -176.2 -152.9 -184.1C-105.8 -192 -52.9 -165.5 -10.1 -151.6C32.7 -137.7 65.4 -136.4 83.3 -119"
						fill="none" stroke="#84f4fff5" stroke-width="8"></path>
				</g>
			</svg>
		</span>
	</div>
</template>

<style scoped>
body {
	height: 100vh;
	margin: 0;
	display: grid;
	place-items: center;
	background: rgb(255, 255, 255);
	background: radial-gradient(circle,
			rgba(255, 255, 255, 0.8169642857142857) 0%,
			rgb(0, 0, 0) 100%);
}

.fistbump {
	font-size: 10rem;
	margin: auto;
}

.bump-options {
	display: flex;
	flex-direction: row;
	justify-content: space-around;
	align-items: center;
	width: 100%;
}

.left-fist,
.right-fist {
	position: relative;
	margin-right: 1rem;
}

.left-bump {
	animation: left-fist 3s cubic-bezier(0.075, 0.82, 0.165, 1);
}

.right-bump {
	animation: right-fist 3s cubic-bezier(0.075, 0.82, 0.165, 1);
}

svg {
	animation: rotate-svg 3s linear infinite;
    position: absolute;
    z-index: 0;
    top: -100px;
    right: -47px;
    background: radial-gradient(circle, rgba(100, 21, 146, 0.377) 10%, rgba(229, 231, 238, 0) 40%);
}

.glow {
	text-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px #fff, 0 0 40px #fff, 0 0 50px #fff, 0 0 60px #fff, 0 0 100px #fff;
}

button {
	font-size: 1rem;
	padding: 0.5rem;
	border-radius: 1rem;
	background: #140514;
	border-color: #862a86;
	color: #fff;
	cursor: pointer;
	transition: all 0.3s ease;
	z-index: 100;
}

@keyframes right-fist {
	0% {
		left: 0;
	}

	40% {
		left: 100px;
	}

	60% {
		left: 180px;
	}

	80% {
		left: -80px;
	}

	100% {
		left: 0;
	}
}

@keyframes left-fist {
	0% {
		right: 0;
	}

	40% {
		right: 100px;
	}

	60% {
		right: 180px;
	}

	80% {
		right: -80px;
	}

	100% {
		right: 0;
	}
}

@keyframes rotate-svg {
	0% {
		transform: rotate(0deg);
	}
	100% {
		transform: rotate(360deg);
	}
}



</style>