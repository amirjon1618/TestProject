<template>
    <div class="flex container mx-auto  max-w-screen-xl flex-wrap sm:flex-nowrap">
        <LeftSidebar />
        <RightSidebar />
    </div>
</template>

<script>
  import LeftSidebar from "./LeftSidebar.vue";
  import RightSidebar from "./RightSidebar.vue";

  export default {
    components: {
    LeftSidebar,
    RightSidebar
}
  }
</script>

<style>

</style>