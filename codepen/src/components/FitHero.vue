<script>

</script>

<template>

    <section class="hero">
        <nav class="nav-head">
            <div class="nav-logo">
                <h2>
                    SZ Fit
                </h2>
            </div>
            <div class="nav-item">
                <a href="#">
                    <h2>
                        Home
                    </h2>
                </a>
                <a href="#">
                    <h2>
                        Blog
                    </h2>
                </a>
                <a href="#">
                    <h2 class="contact-me">
                        Contact Me
                    </h2>
                </a>
            </div>

        </nav>
    </section>



</template>

<style scoped>
:root {
    font-size: 62.5%;
    --main-color: #f6d7b0;
    --main-color-dark: #f5f5f5;
    --main-color-light: #f5f5f5;
    --primary-color: #000000;
}

a {
    color: var(--primary-color);
    text-decoration: none;
}

h2 {
    font-size: 3rem;
    color: #f5f5f5;
    font-weight: bold;
    padding: 1rem 1.2rem;
    border: 1px solid #000000;
    margin: 0;
}

body {
    font-family: 'Cormorant Upright';
    font-style: normal;
    margin: 0;
}

.hero {
    height: 100vh;
    background-image: url('https://images.unsplash.com/photo-1552196563-55cd4e45efb3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1926&q=80');
    background-size: cover;
    background-position: center;
}

nav {
    height: auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.nav-item {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    gap: 40px;
}

.contact-me {
    font-size: 3.5rem;
    height: 100%;
    width: auto;
    background-color: var(--main-color);
    border-radius: 0% 0% 0% 10%;
    border: none;
    box-shadow: 0px 0px 5px 5px rgba(0, 0, 0, 0.81);
}


</style>