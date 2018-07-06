<template>
    <div>
        <div class="logo">
            <div class="container">
              <div class="row justify-content-center">
                <div class="title-head">
                Digital Signing</div>
              </div>
              <div class="row justify-content-center">
                <div class="title-head-second">แพลตฟอร์มลงลายมือชื่ออิเล็กทรอนิกส์ที่น่าเชื่อถือ</div>
              </div>
        </div>
        </div>
        <section_1></section_1>
        <section_2></section_2>
    </div>
</template>

<script>
import section_1 from "./section/section_1";
import section_2 from "./section/section_2";
import Parallax from "vue-parallaxy";

export default {
  name: "Layout",
  components: {
    section_1,
    section_2
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.logo {
  background: url("../assets/Image_42e317c.jpg");
  background-attachment: fixed;
  background-position: center top;
  background-repeat: no-repeat;
  background-size: contain;
  width: 100%;
  height: 400px;
}
.title-head {
  font-size: 4em;
  color: #fff;
  padding-top: 100px;
}
.title-head-second {
  font-size: 2em;
  color: #fff;
  margin-top: 20px;
}
</style>
