<template>
    <div class="flex container mx-auto   xl:container lg:container md:container sm:container flex-wrap md:flex-nowrap">
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