<template>
  <div>
    <div class="navbar-top">
      <div class="container-fluid">
        <img src="../assets/logo_OneAuthen_500px.png" class="logo" alt="" />
        <ul class="super-menu">
          <a href="#"><li>หน้าหลัก</li></a>
          <a href="#"><li>โซลูชั่น</li></a>
          <a href="#"><li>ติดต่อเรา</li></a>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar-top {
  
  width: 100vw;
  height: 65px;
  position: fixed;
  z-index: 2000;
}
.logo {
  width: 110px;
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

.super-menu {
  display: inline-block;
  float: right;
}
.super-menu > a > li {
  display: inline-block;
  width: 150px;
  text-align: center;
  line-height: 45px;
  color:#fff;
  padding: 10px;
  transition: all 0.5s;
  }

  .super-menu > a > li:hover{
  display: inline-block;
  width: 110px;
  text-align: center;
  line-height: 45px;
  color:#EE2524;
  padding-bottom: 5px;
  transition: all 0.5s;
  border-bottom:solid 5px #EE2524;
  border-left:solid 2px #EE2524;
  border-right:solid 2px #EE2524;
  }

ul {
  padding: 0;
  margin: 0;
  list-style: none;
}

</style>
