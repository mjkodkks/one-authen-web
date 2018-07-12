<template>
  <div class="section">
    <div class="last-img">
      <div class="contact-card wow slideInLeft">
        <div class="contact-head">ติดต่อเรา</div>
        <div class="container">
          <b-form @submit="onSubmit">
            <div class="row justify-content-center" style=" margin: 20px 0 20px 0;">
              <div class="col-md-3">
                <div class="head float-right">ชื่อ</div>
              </div>
              <div class="col-md-6">
                <b-form-input id="Input1" type="text" v-model="form.name_user" required ></b-form-input>
              </div>
            </div>
            <div class="row justify-content-center" style=" margin: 20px 0 20px 0;">
              <div class="col-md-3">
                <div class="head float-right">E-mail</div></div>
              <div class="col-md-6">
                <b-form-input id="Input2" type="text" v-model="form.email_user" required p></b-form-input>
              </div>
            </div>
            <div class="row justify-content-center" style=" margin: 20px 0 20px 0;">
              <div class="col-md-3"><div class="head float-right">เบอร์ติดต่อ</div></div>
              <div class="col-md-6">
                <b-form-input id="Input3" type="text" v-model="form.telephone_user" required ></b-form-input>
              </div>
            </div>
            <b-button type="submit" class="send-btn">
              <div>ส่งข้อมูล</div>
            </b-button>
            </b-form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Parallax from "vue-parallaxy";
import WOW from "wow.js";

export default {
  name: "section_3",
  components: {
    Parallax
  },
  data() {
    return {
      form: {
        name_user: "",
        email_user: "",
        telephone_user: ""
      }
    };
  },
  methods: {
    onSubmit(evt) {
      evt.preventDefault();
      var myform = "คุณ " + this.name_user + "เบอร์ติดต่อ " + this.telephone_user 
      //alert(JSON.stringify(this.form));
      var mail = document.createElement("a");
      mail.href = "mailto:info@oneauthen.in.th?subject=ติดต่อ OneAuthen"+"&body=" + encodeURIComponent(myform);

      mail.click();
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.section {
  width: 100%;
  min-height: 600px;
  box-sizing: border-box;
}

.last-img {
  background: url("../../assets/Image_42e317c.jpg");
  background-position: 50% 50%;
  background-repeat: no-repeat;
  background-size: cover;
  width: 100%;
  height: 600px;
  box-sizing: border-box;
  padding: 1%;
}

.contact-card {
  text-align: center;
}

.contact-head {
  color: #fff;
  font-size: 4em;
  margin-top: 20px;
}

.head {
  color: #fff;
  font-size: 2em;
}

.send-btn {
  margin-top: 50px;
  background: transparent;
  border: 3px solid #fff;
  width: 300px;
  padding: 30px;
  font-size: 2em;
  overflow: hidden;
  cursor: pointer;
  transition: 0.08s ease-in;
  outline: 0;
  position: relative;
}



.send-btn:before {
  content: url("../../assets/ICON/bxs-right-arrow.svg");
  position: absolute;
  color: #fff;
  left: 50%;
  opacity: 0;
  font-weight: 900;
  -webkit-transition: all 0.2s ease-in;
}

.send-btn:hover:before {
  left: 80%;
  opacity: 1;
}

.send-btn:hover {
  border-top: 0px #fff solid;
  border-right: 0px #fff solid;
  border-bottom: 0px #fff solid;
  -webkit-transform: scale(1.04, 1.04);
  -webkit-transition: border 0.3s ease-out;
  -webkit-transition: transform 250ms cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
</style>

<style>
.form-control {
  background-color: transparent;
  color: #fff;
  border: none;
  border-bottom: 3px solid #ced4da;
  border-radius: 0;
}
.form-control:focus {
  color: #fff;
  background-color: rgba(0, 0, 0, 0.14);
  border-color: #80bdff;
  outline: 0;
  box-shadow: 0 0 0 0.2rem rgba(0, 123, 255, 0.25);
}

::-webkit-input-placeholder {
  color: #fff;
  opacity: 1; /* Firefox */
}
</style>
