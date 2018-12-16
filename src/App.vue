<template>
  <div id="app">
    <h1>欢迎使用签名生成器</h1>
    <div class="container">
      <div class="form">
        <el-form ref="form" :model="infodata" label-width="120px">
          <el-form-item label="中文名">
            <el-input v-model="infodata.peoples"></el-input>
          </el-form-item>
          <el-form-item label="拼音或英文名">
            <el-input v-model="infodata.names"></el-input>
          </el-form-item>
          <el-form-item label="职位">
            <el-input v-model="infodata.sczy"></el-input>
          </el-form-item>
          <el-form-item label="职位(英文)">
            <el-input v-model="infodata.fanyi"></el-input>
          </el-form-item>
          <el-form-item label="电话T">
            <el-input v-model="infodata.t"></el-input>
          </el-form-item>
          <el-form-item label="传真F">
            <el-input v-model="infodata.f"></el-input>
          </el-form-item>
          <el-form-item label="手机M">
            <el-input v-model="infodata.m"></el-input>
          </el-form-item>
          <el-form-item label="邮箱E">
            <el-input v-model="infodata.e"></el-input>
          </el-form-item>
          <el-form-item label="公司名">
            <el-input v-model="infodata.companyname"></el-input>
          </el-form-item>
          <el-form-item label="公司名(英文)">
            <el-input v-model="infodata.companynameE"></el-input>
          </el-form-item>
          <el-form-item label="部门">
            <el-input v-model="infodata.unit"></el-input>
          </el-form-item>
          <el-form-item label="部门(英文)">
            <el-input v-model="infodata.unitInEn"></el-input>
          </el-form-item>
          <el-form-item label="地址">
            <el-input v-model="infodata.address"></el-input>
          </el-form-item>
          <el-form-item label="地址(英文)">
            <el-input v-model="infodata.addressE"></el-input>
          </el-form-item>
        </el-form>
      </div>
      <div class="preview">
        <div class="previewborder">
          <Preview :yourinfo="infodata"/>
        </div>
      </div>
      <div class="capture-area">
        <el-button class="capture-btn" type="success" @click="captureScreen">生成图像</el-button>
      </div>
      <div id="canvas">
        <div id="canvasborder"></div>
      </div>
    </div>
  </div>
</template>

<script>
import Preview from './components/Preview.vue'
import html2canvas from 'html2canvas'
import { Message } from 'element-ui'
export default {
  name: 'app',
  components: {
    Preview
  },
  data: () => ({
    infodata: {
      peoples: '李亭亭',
      names: 'Li Tingting',
      sczy: '规划主管',
      fanyi: 'Planning Supervisor',
      t: '0731-22837872',
      f: '0731-22837872',
      m: '17716767136',
      e: 'litt@teg.cn',
      unit: '轨道交通事业部',
      unitInEn: 'Rail Transportation Business Unit',
      companyname: '株洲时代新材料科技股份有限公司',
      companynameE: 'ZHUZHOU TIMES NEW MATERIAL TECHNOLOGY CO., LTD.',
      address: '湖南省株洲市天元区黑龙江路569号',
      addressE: 'NO.569Heilongjiang Road,Tianyuan District,Zhuzhou,Hunan,P.R.China'
    },
    canvas: {},
    ifFirstTime: true
  }),
  created () {
    console.log('作者：卢雨龙')
  },
  methods: {
    captureScreen () {
      const _this = this
      if (!this.ifFirstTime) {
        Message({
          type: 'warning',
          message: '图片已经生产，请右键保存'
        })
        return false
      }
      html2canvas(document.querySelector('#main'))
        .then(canvas => {
          _this.ifFirstTime = false
          document.querySelector('#canvasborder').appendChild(canvas)
          Message({
            type: 'success',
            showClose: true,
            message: '图片生产成功，请右键保存图片'
          })
        })
        .catch(err => console.log(err))
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  position: relative;
  padding-left: 600px;
  text-align: left;
}
h1 {
  line-height: 40px;
  text-align: center;
  margin: 50px 0;
}
h1::after {
  content: "by营销团支部";
  font-size: 12px;
  color: #606266;
  padding-left: 20px;
}
.form {
  position: absolute;
  left: 0;
  top: 0;
  z-index: 1;
  width: 370px;
  text-align: center;
  padding-left: 120px;
}
.capture-area::after {
  content: "生产的图片尺寸为720*270,保存时不带边框";
  margin-left: 20px;
  color: #606266;
}
.preview {
  margin-bottom: 50px;
}
.previewborder {
  display: inline-block;
  border: 1px #e4e4e4 solid;
  box-sizing: border-box;
}
#canvas {
  margin-top: 50px;
  border: 1px #e4e4e4 solid;
}
#canvasborder {
  display: inline-block;
  box-sizing: border-box;
  min-height: 270px;
}
</style>
