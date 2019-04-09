<template>
  <div class="index">
    <N1></N1>
    <N2></N2>
  </div>
</template>

<script>
// @ is an alias to /src
import N1 from "@/components/N1.vue";
import N2 from "@/components/N2.vue";

export default {
  name: "index",
  components: {
    N1,
    N2
  }
};
</script>

<style scoped>
</style>
