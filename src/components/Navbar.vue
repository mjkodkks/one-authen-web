<template>
  <div id="section-1">
    <div class="navbar-top" v-scroll="handleScrollnavbar">
      <div class="container-fluid">
        <img src="../assets/logo_OneAuthen_500px.png" class="logo" alt="" v-scroll="handleScrolllogo" v-scroll-to="'#section-1'" />
        <ul class="super-menu" v-scroll="handleScrollsupermenu">
          <a href="#" v-scroll-to="'#section-1'"><li>หน้าหลัก</li></a>
          <a href="#" v-scroll-to="'#section-2'"><li>โซลูชั่น</li></a>
          <a href="#" v-scroll-to="'#section-3'"><li>ติดต่อเรา</li></a>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";

Vue.directive("scroll", {
  inserted: function(el, binding) {
    let f = function(evt) {
      if (binding.value(evt, el)) {
        window.removeEventListener("scroll", f);
      }
    };
    window.addEventListener("scroll", f);
  }
});

export default {
  name: "Navbar",
  methods: {
    handleScrollnavbar: function(evt, el) {
      if (window.scrollY > 50) {
        el.setAttribute("class", "navbar-top-scroll");
      } else el.setAttribute("class", "navbar-top");
    },
    handleScrolllogo: function(evt, el) {
      if (window.scrollY > 50) {
        el.setAttribute("class", "logo-scroll");
      } else el.setAttribute("class", "logo");
    },
    handleScrollsupermenu: function(evt, el) {
      if (window.scrollY > 50) {
        el.setAttribute("class", "super-menu-scroll");
      } else el.setAttribute("class", "super-menu");
    }
  }
};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar-top {
  width: 100vw;
  height: 65px;
  position: fixed;
  z-index: 2000;
  transition: all 0.5s;
}
.navbar-top-scroll {
  width: 100vw;
  height: 65px;
  position: fixed;
  z-index: 2000;
  background: #fff;
  box-shadow: 0 4px 30px 0 rgba(223, 225, 230, 0.5);
  transition: all 0.5s;
}
.logo {
  width: 140px;
  padding: 10px;
  filter: brightness(0) invert(1);
  margin-left: 5%;
  transition: all 1s;
}
.logo:hover {
  width: 110px;
  padding: 10px;
  margin-left: 5%;
  transition: all 1s;
  filter: brightness(1) invert(0);
}

.logo-scroll {
  width: 110px;
  padding: 10px;
  margin-left: 5%;
  transition: all 1s;
}

.super-menu {
  display: inline-block;
  float: right;
}
.super-menu > a > li {
  display: inline-block;
  width: 150px;
  text-align: center;
  line-height: 45px;
  color: #fff;
  padding: 10px;
  transition: all 0.5s;
}

.super-menu > a > li:hover {
  display: inline-block;
  width: 110px;
  text-align: center;
  line-height: 45px;
  color: #ee2524;
  padding-bottom: 5px;
  transition: all 0.5s;
  border-bottom: solid 5px #ee2524;
  border-left: solid 2px #ee2524;
  border-right: solid 2px #ee2524;
}

.super-menu-scroll {
  display: inline-block;
  float: right;
}

.super-menu-scroll > a > li {
  display: inline-block;
  width: 150px;
  text-align: center;
  line-height: 45px;
  color: #ee2524;
  padding: 10px;
  transition: all 0.5s;
}

.super-menu-scroll > a > li:hover  {
  display: inline-block;
  width: 110px;
  text-align: center;
  line-height: 45px;
  color: #ee2524;
  padding: 10px;
  transition: all 0.5s;
    border-bottom: solid 5px #ee2524;
  border-left: solid 2px #ee2524;
  border-right: solid 2px #ee2524;
}

ul {
  padding: 0;
  margin: 0;
  list-style: none;
}
</style>
