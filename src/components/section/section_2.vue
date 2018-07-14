<template>
  <div class="section">
    <div class="container">
      <div class="row justify-content-center" style="margin-top:150px">
        <div class="col-md-5 col-offset-1 col-12">
          <div class="wow bounceIn">
            <div class="profile-card">
              <img src="../../assets/ICON/05.png" alt="" />
              <div>ประหยัดเวลา และลดต้นทุนเอกสารในการทำธุรกรรม</div>
            </div>
          </div>
        </div>
        <div class="col-md-5 col-offset-1 col-12">
          <div class="wow bounceIn">
            <div class="profile-card">
              <img src="../../assets/ICON/12.png" alt="" />
              <div>ตรวจสอบข้อมูลและความน่าเชื่อถือของเอกสารได้ทันที</div>
            </div>
          </div>
        </div>
      </div>
      <div class="row justify-content-center">
        <div class="col-md-5 col-offset-1 col-12">
          <div class="wow bounceIn">
            <div class="profile-card">
              <img src="../../assets/ICON/09.png" alt="" />
              <div>สามารถตรวจสอบ และพิสูจน์เจ้าของลายมือชื่อได้</div>
            </div>
          </div>
        </div>
        <div class="col-md-5 col-offset-1 col-12">
          <div class="wow bounceIn">
            <div class="profile-card">
              <img src="../../assets/ICON/10.png" alt="" />
              <div>มีความน่าเชื่อถือ สอดคล้องตาม พรบ.ธุรกรรมทางอิเล็กทรอนิกส์ พ.ศ.2544 มาตรา 9 และ 26</div>
            </div>
          </div>
        </div>
      </div>
      <div class="row justify-content-center">
        <div class="col-md-5 col-offset-1 col-12">
          <div class="wow bounceIn">
            <div class="profile-card">
              <img src="../../assets/ICON/07.png" alt="" />
              <div>ให้บริการบนมาตรฐาน ISO 20000 และ ISO 27001</div>
            </div>
          </div>
        </div>
      </div>
  
    </div>
  </div>
</template>

<script>
import WOW from "wow.js";

new WOW().init();

export default {
  name: "section_2",

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.section {
  width: 100%;
  box-sizing: border-box;
}

.img-card {
  width: 100%;
}

.card-text {
  margin-top: 10px;
  font-size: 2em;
}

.profile-card {
  text-align: center;
}

.profile-card > img {
  width: 128px;
}

.profile-card div {
  font-size: 1.5em;
  margin: 40px;
}
</style>
