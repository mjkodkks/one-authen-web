<template>
    <div style="padding-top:65px;">
      <div class="imgbanner">
        <img src="../assets/digital signing-banner.jpg" draggable="false" width="100%" alt="">
      </div>
        <section_1></section_1>
        <div class="test"></div>
    </div>
</template>

<script>
import section_1 from "./section/section_1";

export default {
  name: "Layout",
  components: {
    section_1
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.test {
  height: 100vh;
}
.imgbanner {
  width: inherit;
  height: inherit;
}
</style>
