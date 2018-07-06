<template> 
  <div class="section">
     <parallax> 
    <div class="container">
      <div class="row justify-content-center">
        <div class="card-login"><img src="../../assets/logo_OneAuthen_500px.png" class="img-card" alt="fail">
        <div class="card-text" >ทดลองใช้งาน</div>
        </div>
      </div>
    </div>
    </parallax>
  </div>
</template>

<script>
import Parallax from 'vue-parallaxy'

export default {
  name: "section_1",
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
.card-login {
  width: 400px;
  height: 300px;
  text-align: center;
  box-shadow: 0 4px 30px 0 rgba(223, 225, 230, 0.5);
  border-radius: 30px 30px 30px 30px;
  -moz-border-radius: 30px 30px 30px 30px;
  -webkit-border-radius: 30px 30px 30px 30px;
  border: 0px solid #000000;
  padding: 4%;
  display: block;
  margin-top: 30px;
  background: #fff;
}
.img-card {
  width: 100%;
}
.card-text {
  margin-top: 10px;
  font-size: 2em;
}
</style>
