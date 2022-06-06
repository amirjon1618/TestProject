<template>
  <TheHeader />
  <LeftSidebar />
  <RightSidebar />
  <TheFooter />
</template>

<script>
  import TheHeader from "./components/TheHeader.vue";
  import LeftSidebar from "./components/LeftSidebar.vue";
  import RightSidebar from "./components/RightSidebar.vue";
  import TheFooter from "./components/TheFooter.vue";

  export default {
    components: {
    TheHeader,
    LeftSidebar,
    RightSidebar,
    TheFooter
}
  }
</script>

<style>

</style>
