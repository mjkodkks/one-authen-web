<template>
  <div class="section">
       <div class="last-img"></div>
  </div>
</template>

<script>
import Parallax from "vue-parallaxy";

export default {
  name: "section_3",
  components: {
    Parallax
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.section {
  width: 100%;
  height: 400px;
  box-sizing: border-box;
}
.last-img {
  background: url("../../assets/Image_42e317c.jpg");
  background-attachment: fixed;
  background-position: center top;
  background-repeat: no-repeat;
  background-size: contain;
}


</style>
