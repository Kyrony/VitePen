<script>

export default {
    props: ['title', 'description'],
}

</script>

<template>

    <article class="fit-card">
        <div class="fit-description">
            <h3> {{ title }} </h3>
            <p> {{ description }}</p>
        </div>
    </article>

</template>


<style scoped>
.fit-card {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-end;
    width: 60%;
    height: 100%;
    padding: 1rem;
    border: 1px solid #ccc;
    margin-bottom: 1rem;
}

.fit-description {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 50%;
    height: 400px;
}


</style>