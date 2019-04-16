<template>
  <div class="index">
    <mainbg></mainbg>
    <N1></N1>
    <N2></N2>
    <N3></N3>
    <N4></N4>
    <N5></N5>
    <N6></N6>
  </div>
</template>

<script>
// @ is an alias to /src
import Mainbg from "@/components/MainBg.vue"
import N1 from "@/components/N1.vue";
import N2 from "@/components/N2.vue";
import N3 from "@/components/N3.vue";
import N4 from "@/components/N4.vue";
import N5 from "@/components/N5.vue";
import N6 from "@/components/N6.vue";

export default {
  name: "index",
  components: {
    Mainbg,
    N1,
    N2,
    N3,
    N4,
    N5,
    N6
  }
};
</script>

<style scoped>
</style>
