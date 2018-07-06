<template>
  <div class="section">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-md-5 col-offset-1 col-12">
          <div class="profile">
            <img src="../../assets/ICON/01.png" alt="" />
          </div>
        </div>
      </div>
      <div class="col-md-5 col-offset-1 col-12">
        <div class="profile">hello</div>
      </div>
    </div>
  </div>
</template>

<script>
  import Parallax from 'vue-parallaxy'
  
  export default {
    name: "section_2",
    components: {
      Parallax
    }
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .section {
    width: 100%;
    height: 50vh;
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
  
  .profile {
    text-align: center;
  }

</style>
