<script setup>
import PizzaMaker from "./HeaderSection.vue";
export default{
  name:""
components:{PizzaMaker}
}
</script>

<template>
  <h1>{{}}</h1>
  <nav>
    <RouterLink to="/header"> </RouterLink>
  </nav>
  <main></main>
</template>

<style scoped></style>
