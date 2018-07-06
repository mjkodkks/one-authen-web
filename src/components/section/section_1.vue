<template> 
  <div class="section">
    <div class="container">
      <div class="row justify-content-center">
        <div class="card-login"><img src="../../assets/logo_OneAuthen_500px.png" class="img-card" alt="fail">
        <div class="card-text" >ทดลองใช้งาน</div>
        </div>
      </div>
      <div class="row justify-content-center"><div class="underline"></div></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "section_1",
  components: {
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
  margin-top: 100px;
  background: #fff;
  transition: all 0.5s;
  cursor: pointer;
}
.card-login:hover .img-card{
filter: brightness(0) invert(1);
}

.card-login:hover .card-text{
  color:#fff;
  font-size: 3em;
  transition: all 0.8s;
}

.card-login:hover{
background: #EE2524;
transition: all 0.5s;
-webkit-transform: scale(1.04, 1.04);
}

.img-card {
  width: 100%;
}
.card-text {
  margin-top: 10px;
  font-size: 2em;
  transition: all 0.8s;
}
.underline {
  border-bottom: solid red 5px;
  width: 100px;
  padding: 20px 0 20px 0;
  border-radius: 0px 0px 5px 5px;
}

</style>
