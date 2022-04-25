<script>


export default {
    data() {
        return {
            current:"home",
            pages: [
                { id:"home", title:"Home", icon:"home" },
                { id:"search", title:"Search", icon:"search" },
                { id:"notifications", title:"Notifications", icon:"notifications" },
                { id:"favorites", title:"Favorites", icon:"favorite" },
                { id:"profile", title:"Your Profile", icon:"account_circle" },
            ]
        }
    },
    methods: {
        changeCurrent(page) {
            document.body.classList.remove(this.current);
            this.current = page.id;
            document.body.classList.add(this.current);
        }
    }
}

</script>


<template>

    <nav class="menu">
        <a v-for="page in pages" @click="changeCurrent(page)" class="nav-item" :class="page.id, { chosen: current == page.id }" :href="'#'+ page.id"><span class="material-icons">{{ page.icon }}</span></a>
    </nav>

</template>


<style scoped>

body {
	width: 100%;
	height: 100vh;
	display: flex;
	justify-content: flex-end;
	align-items: center;
    margin: 0%;
    background-color: rgb(0, 0, 0);
}

a {
	text-decoration: none;
	font-family: sans-serif;
	text-transform: lowercase;
	font-size: 1em;
}

.menu {
	display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    height: 250px;
    padding: 10px;
    border-radius: 15px 0 0 15px;
    flex-direction: column;
	background: rgb(0, 0, 0);
}

.nav-item {
    height: 40px;
    width: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.material-icons {
    font-size: 2em;
    color: black;
}

.nav-item:hover {
    border-radius: 50%;
    box-shadow: 0px 0px 20px 10px rgba(255, 255, 255, 0.81);
}

/* Direct vars */

.home {
    background: white;
}

.notifications {
    background: blue;
}

.favorites {
    background: rgb(124, 6, 6);
}

.profile {
    background: rgb(52, 21, 126);
}

.search {
    background: rgb(0, 161, 73);
}

.chosen {
    border-radius: 50%;
}

</style>
