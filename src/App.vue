<template>
  <TheHeader />
  <ParentSidebar />
  <TheFooter />
</template>

<script>
  import TheHeader from "./components/TheHeader.vue";
  import ParentSidebar from "./components/ParentSidebar.vue"
  import TheFooter from "./components/TheFooter.vue";

  export default {
    components: {
    TheHeader,
    ParentSidebar,
    TheFooter
}
  }
</script>

<style>

</style>
