<script>

export default {
    data () {
        return {
            colors: [
                '#f44336',
                '#e91e63',
                '#9c27b0',
                '#673ab7',
                '#3f51b5',
                '#2196f3',
                '#03a9f4',
                '#00bcd4',
                '#009688',
                '#4caf50',
                '#8bc34a',
            ],
            shakes: 0,
            fruit: false,
        }
    },
    methods: {
        increase() {
            this.shakes++;
            this.fruit = !this.fruit;
            if (this.shakes === 5) {
                this.shakes = 0;
                let color = this.colors[Math.floor(Math.random() * this.colors.length)];
                document.getElementById('colorful').style.background = color;
            }
        }
    },
    mounted () {
        onmousemove = function(e){
            var x = e.clientX;
            var y = e.clientY;
            let height = window.innerHeight;
            let width = window.innerWidth;
            let lefty = (x-width/2)/2;
            let topy = (y-height/2)/2;
            let rotatey = (lefty * (topy/width)) * 1.5;
            var shake = document.getElementById("shake");
            shake.style.transform = `rotate( ${ -rotatey + 'deg'})`;
            if (x < width/2) { shake.style.left = lefty + "px"; }
            if (x > width/2) { shake.style.left = lefty/2 + "px"; }
            if (y > height/2) { shake.style.top = topy + "px"; }
            if (y < height/2) { shake.style.top = topy + "px"; }
        }
    }
}


</script>

<template>
    <section>
        <div id="colorful"></div>
        <h1> Shake it to the left! Shake it to the right! </h1>
        <div @mouseenter="increase" class="top">
            <span :class="{flip : fruit}" ><img src="https://img.icons8.com/external-filled-outline-icons-pause-08/344/external-fruit-autumn-filled-outline-icons-pause-08.png" alt=""></span>
            <span :class="{flip : fruit}" ><img src="https://img.icons8.com/external-colored-outline-lafs/344/external-fruit-flavors-colored-outline-part-1-colored-outline-lafs.png" alt=""></span>
            <span :class="{flip : fruit}" ><img src="https://img.icons8.com/color/344/plum.png" alt=""></span>
            <span :class="{flip : fruit}" ><img src="https://img.icons8.com/external-creatype-filed-outline-colourcreatype/344/external-fruit-morning-breakfast-filed-outline-creatype-filed-outline-colourcreatype.png" alt=""></span>
        </div>
        <div @mouseenter="increase" class="bottom">
            <span :class="{flip : fruit}" ><img src="https://img.icons8.com/color/344/plum.png" alt=""></span>
            <span :class="{flip : fruit}" ><img src="https://img.icons8.com/external-creatype-filed-outline-colourcreatype/344/external-fruit-morning-breakfast-filed-outline-creatype-filed-outline-colourcreatype.png" alt=""></span>
            <span :class="{flip : fruit}" ><img src="https://img.icons8.com/external-colored-outline-lafs/344/external-fruit-flavors-colored-outline-part-1-colored-outline-lafs.png" alt=""></span>
            <span :class="{flip : fruit}" ><img src="https://img.icons8.com/external-filled-outline-icons-pause-08/344/external-fruit-autumn-filled-outline-icons-pause-08.png" alt=""></span>
        </div>
        <p class="shake">
            <span id="shake">🥤</span>
        </p>
    </section>
</template>


<style scoped>

body,
html {
	height: 100%;
	display: grid;
	background: radial-gradient(
		circle,
        rgb(255, 255, 255) 0%,
		rgba(255, 255, 255, 0.8169642857142857) 20%,
		rgb(255, 29, 29) 100%
	);
}

section {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    height: 100%;
}

h1 {
    position: fixed;
    font-size: 3rem;
    font-weight: bold;
    color: rgb(0, 0, 0);
    left: 50%;
    top: 5%;
    transform: translateX(-50%);
}

span:nth-child(2n) {
    animation: bounce 2s infinite;
}

p {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    width: 100%;
}

#colorful {
    opacity: 0.5;
    position: absolute;
    width: 100%;
    height: 100%;
}

.top,
.bottom {
    position: absolute;
    left: 0;
    width: 100%;
    height: 50%;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
}

.top {
    top: 0;
}

.bottom {
    bottom: 0;
}

img {
    width: 100px;
}

img:nth-child(2n + 1) {
    animation: bounce2 2s infinite;
}

.flip {
    transform: scaleX(-1);
}

.shake {
	font-size: 10rem;
	margin: auto;
}

#shake {
    position: relative;
}

@keyframes bounce {
    0% {
        transform: translateY(0);
        transform: translateX(0px);
    }
    25% {
        transform: translateX(10px);
    }
    50% {
        transform: translateY(-10px);
    }
    75% {
        transform: translateX(-10px);
    }
    100% {
        transform: translateY(0);
    }
}

@keyframes bounce2 {
    0% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(20px);
    }
    100% {
        transform: translateY(0);
    }
}

@media screen and (max-width: 600px) {
    h1 {
        font-size: 1rem;
    }
}

</style>