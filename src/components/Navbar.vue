<template>
  <div id="section-1">
    <div class="navbar-top" v-scroll="handleScrollnavbar">
      <div class="container-fluid">
        <img src="../assets/logo_OneAuthen_500px.png" class="logo" alt="" v-scroll="handleScrolllogo" v-scroll-to="'#section-1'" />
          
        <ul v-if="!ifmobile" class="super-menu" v-scroll="handleScrollsupermenu">
          <a href="#" v-scroll-to="'#section-1'">
            <li>หน้าหลัก</li>
          </a>
          <a href="#" v-scroll-to="'#section-2'" class="sub-menu">
            <li>โซลูชั่น <img v-scroll="handleScrolltri" src="../assets/ICON/bx-play.svg" class="img-sub-menu"> </li>
            <div class="animated bounceIn content-list">
                <a href="">certification</a>
                <a href="">digital signing</a>
              </div>            
          </a>
          <a href="#" v-scroll-to="'#section-3'">
            <li>ติดต่อเรา</li>
          </a>
        </ul>
        <ul v-else-if="clicked === true" class="super-menu-mobile" v-scroll="handleScrollsupermenu">
          <a class="animated fadeIn" style="display:block" href="#" v-scroll-to="'#section-1'">
            <li>หน้าหลัก</li>
          </a>
          <a class="animated fadeIn" style="display:block" href="#" v-scroll-to="'#section-2'">
            <li @click="collapseSubmenu">โซลูชั่น </li>
            <div v-show="clicked_submenu" class="animated fadeIn content-list-mobile">
                <a href="">certification</a>
                <a href="">digital signing</a>
              </div>  
          </a>
          <a class="animated fadeIn" style="display:block" href="#" v-scroll-to="'#section-3'">
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
      clicked: false,
      clicked_submenu: false
    };
  },
  methods: {
    handleScrollnavbar: function(evt, el) {
      if (window.scrollY > 50 && !this.clicked) {
        //console.log(this.clicked);
        el.setAttribute("class", "navbar-top-scroll");
      } else el.setAttribute("class", "navbar-top");

      if (window.scrollY <= 50 && this.clicked) {
        this.collapseBurger();
      }
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
    },
    handleHamberger: function(evt, el) {
      if (window.scrollY > 50) {
        el.setAttribute("class", "burger-position-mobile");
      } else el.setAttribute("class", "burger-position");
    },
    handleScrolltri: function(evt, el) {
      if (window.scrollY > 50) {
        el.setAttribute("class", "img-sub-menu-scroll");
      } else el.setAttribute("class", "img-sub-menu");
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
    },
    collapseSubmenu() {
      this.clicked_submenu = !this.clicked_submenu;
    }
  }
};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
a {
  display: inline-block;
}
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
  margin-top: 1%;
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
  margin-left: 10%;
  cursor: pointer;
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
  width: 150px;
  text-align: center;
  line-height: 45px;
  color: #ee2524;

  transition: all 0.5s;
  border-bottom: solid 5px #ee2524;
  border-left: solid 2px #ee2524;
  border-right: solid 2px #ee2524;
  background: rgb(0, 0, 0, 0.24);
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

.super-menu-scroll > a > li:hover {
  display: inline-block;
  width: 110px;
  text-align: center;
  line-height: 45px;
  color: #ee2524;
  padding: 5px;
  padding-bottom: 10px;
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

.content-list {
  display: none;
  position: absolute;
  top: 67px;
  right: 167px;
  min-width: 200px;
  height: auto;
  border: solid 2px #fefefe;
  background: #ffff;
  transition: all 0.5s;
  font-size: 16px;
  text-decoration: none;
  line-height: 45px;
  box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.14),
    0 3px 1px -2px rgba(0, 0, 0, 0.12), 0 1px 5px 0 rgba(0, 0, 0, 0.2);
  border-radius: 2px;
  text-transform: uppercase;
}

.content-list::after {
  content: "";
  display: block;
  position: absolute;
  width: 20px;
  height: 20px;
  top: -6px;
  right: 7px;
  transform: rotate(45deg);
  background: #fff;
}

.content-list a {
  text-decoration: none;
  border-bottom: solid 2px #f8f8f8;
  padding-left: 15px;
  color: #2c3e50;
}

.content-list a::before {
  content: "";
  display: block;
  position: absolute;
  border-left: solid 5px red;
  left: 0;
  height: 0px;
  transition: all 0.3s;
}

.content-list a:hover {
  color: #f03938;
}

.content-list a:hover::before {
  height: 45px;
  display: block;
  transition: all 0.5s;
}

.sub-menu {
  display: relative;
}

.sub-menu:hover .content-list {
  display: block;
}

.sub-menu:hover .content-list a {
  display: block;
  text-align: left;
}

.img-sub-menu {
  transform: rotate(90deg);
  filter: brightness(0) invert(1);
  transition: all 0.8s;
}

.img-sub-menu-scroll {
  transform: rotate(90deg);
  filter: grayscale(1);
  transition: all 0.8s;
}

.sub-menu:hover img {
  filter: none;
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
  .super-menu > a > li {
    width: 100%;
    transition: none;
  }
  .super-menu > a > li:hover {
    width: 100%;
    transition: none;
  }
  .burger-position {
    display: block;
    position: absolute;
    top: 10px;
    right: 5px;
    transition: all 0.5s;
  }
  .super-menu-mobile {
    background: #d60103;
    position: absolute;
    left: 0;
    right: 0;
    top: 65px;
  }
  .super-menu-mobile > a > li {
    display: inline-block;
    width: 100%;
    text-align: center;
    line-height: 45px;
    color: #fff;
    padding: 10px;
    transition: all 0.5s;
  }
  .super-menu-mobile > a > li:hover {
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
  .super-menu-scroll > a > li {
    display: inline-block;
    width: 100%;
    text-align: center;
    line-height: 45px;
    background: #d60103;
    color: #fff;
    padding: 10px;
    transition: all 0.5s;
  }
  .super-menu-scroll > a > li:hover {
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
  .content-list-mobile {
    display: block;
    width: 100%;
    background: #f03938;

  }
  .content-list-mobile a{
    display: block;
    text-align: center;
    padding: 8px;
    color: #fff;
    text-decoration: none !important;
  }

}
</style>
<style>
 a {
   text-decoration: none !important;
 }
</style>

