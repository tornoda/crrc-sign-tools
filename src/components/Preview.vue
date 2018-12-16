<template>
  <div class="main" id="main" style="margin: 0px;padding: 0px;">
    <div class="cotton">
      <div class="cotton_left">
        <span class="peoples">{{yourinfo.peoples}}</span>
        <span class="names">{{yourinfo.names}}</span>
        <span class="sczy">{{yourinfo.sczy}}</span>
        <span class="fanyi">{{yourinfo.fanyi}}</span>
      </div>
      <div class="cotton_right">
        <div>
          <span class="ziti">T</span>
          <span class="maohao">&nbsp;:&nbsp;</span>
          <span class="shuzi">{{yourinfo.t}}</span>
        </div>

        <div>
          <span class="ziti">F</span>
          <span class="maohao">&nbsp;:&nbsp;</span>
          <span class="shuzi">{{yourinfo.f}}</span>
        </div>
        <div>
          <span class="ziti">M</span>
          <span class="maohao">&nbsp;:&nbsp;</span>
          <span class="shuzi">{{yourinfo.m}}</span>
        </div>
        <div>
          <span class="ziti">E</span>
          <span class="maohao">&nbsp;:&nbsp;</span>
          <span class="shuzi">{{yourinfo.e}}</span>
        </div>
      </div>
    </div>
    <div class="hr"></div>
    <div class="clear"></div>
    <div class="logo">
      <div class="logo_left">
        <img src="../assets/logo.png" width="190" height="64">
        <span class="wangzhi">www.csrzic.com</span>
      </div>
      <div class="logo_right">
        <div>
          <span class="title1">
            <span class="title1-left">{{yourinfo.companyname}}</span>
            <span class="unit">{{yourinfo.unit}}</span>
          </span>
        </div>
        <div>
          <span class="title2">{{yourinfo.companynameE}}</span>
        </div>
        <div>
          <span class="title2">{{yourinfo.unitInEn}}</span>
        </div>
        <div>
          <span class="title3">{{yourinfo.address}}</span>
        </div>
        <div>
          <span class="title4">{{yourinfo.addressE}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Preview',
  props: {
    yourinfo: Object,
    default: {
      // peoples: "李亭亭",
      // names:"Li Tingting",
      // sczy: "规划主管",
      // fanyi:"Planning Supervisor",
      // t:"0731-22837872",
      // f:"0731-22837872",
      // m:"17716767136",
      // e:"litt@teg.cn",
      // unit: "轨道交通事业部",
      // unitInEn:"Rail Transportation Business Unit",
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.main {
  height: 270px;
  width: 720px;
  margin-right: auto;
  margin-left: auto;
  margin-top: 20px;
}

.main .cotton {
  width: 100%;
}

.main .cotton .cotton_left {
  float: left;
  height: 105px;
  width: 220px;
  margin-top: 15px;
  margin-left: 20px;
}

.main .cotton .cotton_left .peoples {
  font-size: 22px;
  display: block;
  float: left;
  height: 25px;
  width: 100%;
}

.main .cotton .cotton_left .names {
  font-size: 16px;
  color: #818285;
  display: block;
  float: left;
  width: 100%;
  margin-top: 5px;
}

.main .cotton .cotton_left .sczy {
  display: block;
  width: 100%;
  font-size: 16px;
  float: left;
}

.main .cotton .cotton_left .fanyi {
  font-size: 12px;
  color: #818285;
  display: block;
  float: left;
  width: 100%;
}

.main .cotton .cotton_right {
  float: left;
  height: 105px;
  width: 470px;
  margin-top: 15px;
}

// .main .cotton .cotton_right div {
// }

.main .cotton .cotton_right div .ziti {
  font-size: 14px;
  line-height: 20px;
  color: #f00;
}

.main .cotton .cotton_right div .maohao {
  font-weight: bold;
}

.main .cotton .cotton_right div .shuzi {
  font-size: 14px;
  letter-spacing: 1px;
}

.main .hr {
  width: 90%;
  background-color: #bdbec0;
  height: 2px;
  margin-right: auto;
  margin-left: 15px;
  float: left;
  margin-top: 10px;
}

.main .clear {
  clear: both;
}

.main .logo {
  width: 100%;
}

.main .logo .logo_left {
  float: left;
  height: 100px;
  width: 220px;
  margin-top: 15px;
  margin-left: 20px;
}

.main .logo .logo_left img {
  margin-top: 5px;
}

.main .logo .logo_left .wangzhi {
  color: #818285;
  font-weight: bold;
  font-size: 14px;
  display: block;
  margin-top: 8px;
}

.main .logo .logo_right {
  height: 100px;
  float: left;
  margin-top: 15px;
  width: 470px;
}

.main .logo .logo_right div .title1 {
  font-size: 16px;
  line-height: 20px;
  font-weight: bold;
}

.main .logo .logo_right div .title2 {
  font-size: 12px;
  line-height: 25px;
  font-weight: bold;
}

.main .logo .logo_right div .title3 {
  font-size: 14px;
  line-height: 25px;
}

.main .logo .logo_right div .title4 {
  font-size: 12px;
  line-height: 25px;
  color: #818285;
}
// .title1-left {
//   margin-right: 40px;
// }
.unit {
  margin-left: 40px;
}
</style>
