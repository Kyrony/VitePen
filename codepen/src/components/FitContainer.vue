<script>
import FitType from "./FitType.vue";

export default {
  components: {
    FitType
  }
};

</script>

<template>
    <section class="fit-container">
        <FitType class="workout" title="this is a title" description="this is a description"></FitType>
        <FitType></FitType>
        <FitType></FitType>
    </section>
</template>

<style scoped>

.fit-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
}

.workout {
    background-image: url("https://images.unsplash.com/photo-1518791841217-8f162f1e1131?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60");
}

</style>
