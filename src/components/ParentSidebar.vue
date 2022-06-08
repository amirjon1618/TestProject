<template>
    <div class="flex container mx-auto px-4 max-w-screen-xl gap-x-10">
        <LeftSidebar />
        <RightSidebar />
        <h1></h1>
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