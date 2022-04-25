<script>
export default {
    data() {
        return {
            figures: [
                {
                    id:'01', image:"https://assets.codepen.io/652/jordan-bigelow-X5VoG4MA5aI-unsplash.jpg", caption:"Puppy: Bruce (10 Weeks)"
                },
                {
                    id:'02', image:"https://assets.codepen.io/652/karsten-winegeart-NE0XGVKTmcA-unsplash.jpg", caption:"Puppy: Barney (9 Weeks)"
                },
                {
                    id:'03', image:"https://assets.codepen.io/652/kabo-NjWZ07sPEJE-unsplash.jpg", caption:"Cat: Walter (5 Years)"
                },
                {
                    id:'04', image:"https://assets.codepen.io/652/giacomo-lucarini-7M0SG3ZKdlE-unsplash.jpg", caption:"Dog: Miss Sunshine (2 Years)"
                },
                {
                    id:'05', image:"https://assets.codepen.io/652/sergey-semin-Y0WXj3xqJz0-unsplash.jpg", caption:"Kitten: Reese (8 Weeks)"
                },
            ],
        }
    },
    methods: {
        change(index) {
            if (index > 2)
                console.log(index),
                this.current = this.figures[0],
                this.figures.shift(),
                this.figures.push(this.current);
            else if (index < 2)
                console.log(index),
                this.current = this.figures[4],
                this.figures.pop(),
                this.figures.unshift(this.current);
        }
    },
}
</script>

<template>
    <div class="gallery">
        <figure v-for="(figure, i) in figures" @click="change(i)" :index="i">
            <img :src="figure.image">
            <figcaption>{{ figure.caption }} </figcaption>
        </figure>
    </div>
</template>


<style scoped>

body {
    background-color: rgb(14, 8, 1);
    font-family: Avenir, Helvetica, Arial, sans-serif;
    text-align: center;
    color: #ffffff;
}

.gallery {
margin-top: 20%;
display: grid;
grid-template-columns: 1fr 1.5fr 2fr 1.5fr 1fr;
grid-template-rows: 1fr;
grid-column-gap: 0px;
grid-row-gap: 0px;
animation: fadeIn 1s ease-in;
}

figure img {
    width: 100%;
    height: auto;
    border-radius: 20px;
    box-shadow: 0px 0px 10px rgba(224, 158, 255, 0.61);
}

figure img:hover {
    box-shadow: 0px 0px 10px rgba(224, 158, 255, 0.61);
    cursor: pointer;
}
</style>