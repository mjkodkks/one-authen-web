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
      <vue-particles class="particle-top" color="#BB1F20"></vue-particles>
    </div>
    <section_1 id="section-2"></section_1>
    <section_2></section_2>
    <section_3 id="section-3"></section_3>
  </div>
</template>

<script>
import Vue from "vue"
import section_1 from "./section/section_1";
import section_2 from "./section/section_2";
import section_3 from "./section/section_3";
import VueParticles from 'vue-particles';

Vue.use(VueParticles)

export default {
  name: "Layout",
  components: {
    section_1,
    section_2,
    section_3
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.logo {
  background: url("../assets/Image_42e317c.jpg");
  background-attachment: fixed;
  background-position: center top;
  background-repeat: repeat;
  background-size: contain;
  box-shadow: 0 2px 2px 0 rgba(0,0,0,0.14), 0 3px 1px -2px rgba(0,0,0,0.12), 0 1px 5px 0 rgba(0,0,0,0.2);
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
  margin-bottom: 50px;
}

.particle-top {
  position: absolute;
  top: 0;
  right: 0;
  left: 0;
  height: 313px;
}

.particle-bottom {
  position: absolute;
  right: 0;
  left: 0;
  bottom: 0;
  height: 313px;
}

@media screen and (max-width: 500px) {
  .logo {
  background: url("../assets/Image_42e317c.jpg");
  background-attachment: fixed;
  background-position: center top;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
}
  .title-head {
  font-size: 3em;
  color: #fff;
  padding-top: 40vh;
}

.title-head-second {
  font-size: 1em;
  color: #fff;
  margin-top: 20px;
  margin-bottom: 50px;
}

.particle-top {
  position: absolute;
  top: 0;
  right: -20;
  left: 0;
  height: 100vh;
}
}
</style>
