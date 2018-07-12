<template>
  <div id="section-1">
    <div class="navbar-top" v-scroll="handleScrollnavbar">
      <div class="container-fluid">
        <img src="../assets/logo_OneAuthen_500px.png" class="logo" alt="" v-scroll="handleScrolllogo" v-scroll-to="'#section-1'" />
        <ul v-if="!ifmobile" class="super-menu" v-scroll="handleScrollsupermenu">
          <a href="#" v-scroll-to="'#section-1'">
            <li>หน้าหลัก</li>
          </a>
          <a href="#" v-scroll-to="'#section-2'">
            <li>โซลูชั่น</li>
          </a>
          <a href="#" v-scroll-to="'#section-3'">
            <li>ติดต่อเรา</li>
          </a>
        </ul>
        <ul v-else-if="clicked === true" class="super-menu-mobile" v-scroll="handleScrollsupermenu">
          <a href="#" v-scroll-to="'#section-1'">
            <li>หน้าหลัก</li>
          </a>
          <a href="#" v-scroll-to="'#section-2'">
            <li>โซลูชั่น</li>
          </a>
          <a href="#" v-scroll-to="'#section-3'">
            <li>ติดต่อเรา</li>
          </a>
        </ul>
        <div v-scroll="handleHamberger" class="burger-position">
          <button v-if="ifmobile" v-bind:class="[ this.clicked ? hambergerActive : hambergerDefault]" @click="collapseBurger()" type="button">
            <span class="hamburger-box">
              <span class="hamburger-inner"></span>
            </span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Vue from "vue";
  import hambergers from "../../node_modules/hamburgers/dist/hamburgers.min.css";
  
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
    mounted() {
      window.addEventListener("resize", this.handleResize);
      this.handleResize();
    },
    destroyed() {
      window.removeEventListener("resize", this.handleResize);
    },
    data() {
      return {
        ifmobile: false,
        hambergerActive: "hamburger hamburger--spin is-active",
        hambergerDefault: "hamburger hamburger--spin",
        window: {
          width: 0,
          height: 0
        },
        clicked: false
      };
    },
    methods: {
      handleScrollnavbar: function(evt, el) {
        if (window.scrollY > 50 && !this.clicked) {
          console.log(this.clicked);
          el.setAttribute("class", "navbar-top-scroll")
        } else el.setAttribute("class", "navbar-top")

        if(window.scrollY <= 0 && this.clicked) {
          this.collapseBurger()
        }

      },
      handleScrolllogo: function(evt, el) {
        if (window.scrollY > 50) {
          el.setAttribute("class", "logo-scroll")
        } else el.setAttribute("class", "logo")
      },
      handleScrollsupermenu: function(evt, el) {
        if (window.scrollY > 50) {
          el.setAttribute("class", "super-menu-scroll")
        } else el.setAttribute("class", "super-menu")
      },
      handleHamberger: function(evt, el) {
        if (window.scrollY > 50) {
          el.setAttribute("class", "burger-position-mobile")
        } else el.setAttribute("class", "burger-position")
      },
      handleResize() {
        this.window.width = window.innerWidth;
        this.window.height = window.innerHeight;
  
        if (this.window.width <= 500) {
          this.ifmobile = true;
        } else this.ifmobile = false;
      },
      collapseBurger() {
        this.clicked = !this.clicked;
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
    cursor: pointer;
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
    cursor: pointer;
    transition: all 1s;
  }
  
  .super-menu {
    display: inline-block;
    float: right;
  }
  
  .super-menu>a>li {
    display: inline-block;
    width: 150px;
    text-align: center;
    line-height: 45px;
    color: #fff;
    padding: 10px;
    transition: all 0.5s;
  }
  
  .super-menu>a>li:hover {
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
  
  .super-menu-scroll>a>li {
    display: inline-block;
    width: 150px;
    text-align: center;
    line-height: 45px;
    color: #ee2524;
    padding: 10px;
    transition: all 0.5s;
  }
  
  .super-menu-scroll>a>li:hover {
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
  
  @media screen and (max-width: 500px) {
    .super-menu {
      background: #d60103;
      position: absolute;
      left: 0;
      right: 0;
      top: 64px;
      display: none;
    }
    .navbar-top {
      background: #fff;
      box-shadow: 0 4px 30px 0 rgba(223, 225, 230, 0.5);
      height: 75px;
    }
    .super-menu>a>li {
      width: 100%;
      transition: none;
    }
    .super-menu>a>li:hover {
      width: 100%;
      transition: none;
    }
    .burger-position {
      display: block;
      position: absolute;
      top: 10px;
      right: 5px;
    }
    .super-menu-mobile {
      background: #d60103;
      position: absolute;
      left: 0;
      right: 0;
      top: 65px;
    }
    .super-menu-mobile>a>li {
      display: inline-block;
      width: 100%;
      text-align: center;
      line-height: 45px;
      color: #fff;
      padding: 10px;
      transition: all 0.5s;
    }
    .super-menu-mobile>a>li:hover {
      display: inline-block;
      width: 100%;
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
      background: #d60103;
      position: absolute;
      left: 0;
      right: 0;
      top: 64px;
    }
    .super-menu-scroll>a>li {
      display: inline-block;
      width: 100%;
      text-align: center;
      line-height: 45px;
      background: #d60103;
      color: #fff;
      padding: 10px;
      transition: all 0.5s;
    }
    .super-menu-scroll>a>li:hover {
      display: inline-block;
      width: 100%;
      text-align: center;
      line-height: 45px;
      color: #ee2524;
      padding: 10px;
      transition: all 0.5s;
      border-bottom: solid 5px #ee2524;
      border-left: solid 2px #ee2524;
      border-right: solid 2px #ee2524;
    }
    .logo-scroll {
      width: 110px;
      padding: 10px;
      margin-left: 5%;
      cursor: pointer;
      transition: all 1s;
      filter: brightness(1) invert(0);
    }
    .logo {
      filter: brightness(1) invert(0);
    }
    .burger-position-mobile {
      top: 5px;
      display: block;
      position: absolute;
      right: 5px;
      transition: all 0.5s;
    }
    ul {
      border-bottom: #fefefe solid;
    }
  }
</style>
