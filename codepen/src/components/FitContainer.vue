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
        <FitType class="workout-1" title="this is a title" description="this is a description"></FitType>
        <FitType class="workout-2" title="this is a title" description="this is a description"></FitType>
        <FitType class="workout-3" title="this is a title" description="this is a description"></FitType>
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
    padding: 3rem 0rem;
}

.workout-1 {
  background-image: url("https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80");
  background-size: cover;
  background-position: center;
}

.workout-2 {
  background-image: url("https://images.unsplash.com/photo-1517836357463-d25dfeac3438?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80");
  background-size: cover;
  background-position: center;
}

.workout-3 {
  background-image: url("https://images.unsplash.com/photo-1579126038374-6064e9370f0f?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1131&q=80");
  background-size: cover;
  background-position: center;
}


</style>
