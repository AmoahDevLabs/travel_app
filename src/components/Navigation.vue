<template>
  <div id="nav">
    <AppLink id="logo" to="/">Julia Travels</AppLink>
    <AppLink
      v-for="destination in destinations"
      :key="destination.id"
      :to="{
        name: 'DestinationShow',
        params: { id: destination.id, slug: destination.slug },
      }"
    >
      {{ destination.name }}
    </AppLink>
    <AppLink :to="{name: 'Protected'}">Dashboard</AppLink>
    <AppLink to="https://amdevlab.pythonanywhere.com">Amoah DevLabs</AppLink>
  </div>
</template>

<style lang="css">
/* #nav .vue-school-active-link{
        border-bottom: 2px solid salmon;
    } */
/* Adding a custome style for router */
</style>

<script>
import sourceData from "@/data.json";
import AppLink from "./AppLink.vue";
export default {
    data() {
        return {
            destinations: sourceData.destinations,
        };
    },
    components: { AppLink }
};
</script>
