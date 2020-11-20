<template>
  <div id="DataOverview">
    <div class="header">
      <div class="header-1">
        <el-row :gutter="60">
          <el-col :span="6">
            <div class="grid-content bg-purple">
              <p>
                <span class="ling">0</span>
                <img src="../../img/tu3.png" />
              </p>
              <p class="dds1">今日订单总数</p>
            </div>
          </el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple">
              <p>
                <span class="ling">90.00</span>
                <img src="../../img/tu3.png" />
              </p>
              <p class="dds2">今日订单总额</p>
            </div>
          </el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple">
              <p>
                <span class="ling">0</span>
                <img src="../../img/tu3.png" />
              </p>
              <p class="dds3">今日订单总数</p>
            </div>
          </el-col>
          <el-col :span="6">
            <div class="grid-content bg-purple">
              <p>
                <span class="ling">0</span>
                <img src="../../img/tu3.png" />
              </p>
              <p class="dds4">今日订单总数</p>
            </div>
          </el-col>
        </el-row>
        <div class="ddtj">
          <p class="p">订单统计</p>
          <template>
            <p class="black">
              今日
              <span class="blue">本周</span> 本月
            </p>
            <div class="block">
              <el-date-picker
                class="sj"
                v-model="value"
                type="daterange"
                start-placeholder="开始日期"
                end-placeholder="结束日期"
                :default-time="['00:00:00', '23:59:59']"
              ></el-date-picker>
            </div>
          </template>
          <div class="llt">
            <div class="tu1">
              <img src="../../img/tu6.png" width="13%" />
              <img src="../../img/tu4.png" width="70%" class="lltu" />
            </div>
            <p class="jyz">近一周订单统计</p>
          </div>
          
        </div>
      </div>
    </div>
  </div>
</template>
<style>
#DataOverview {
  text-align: center;
  margin-top: 20px;
  background: #f2f2f2;
}
.blue{
  color: #128fe9;
}
.header {
  background: #fff;
  width: 95%;
  margin: 20px 0 20px 50px;
}
.header-1 {
  padding-top: 70px;
  margin-left: 50px;
  width: 90%;
}
.el-row {
  margin-bottom: 20px;
}
.el-col {
  border-radius: 4px;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  border: 1px solid darkgrey;
  background: #fff;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  border-radius: 4px;
  min-height: 100px;
}
.grid-content > p {
  font-weight: 500;
  color: #fff;
}
.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}
.dds1 {
  background: #67cccc;
  border: 1px solid #67cccc;
}
.dds2 {
  background: #349aff;
  border: 1px solid #349aff;
}
.dds3 {
  background: #ffcc9a;
  border: 1px solid #ffcc9a;
}
.dds4 {
  background: #c9c9c9;
  border: 1px solid #c9c9c9;
}
.ling {
  color: #000;
  font-size: 30px;
  font-weight: bold;
}
.p {
  float: left;
}
</style>
<script>
export default {
    name:"DataOverview",
    data(){
        return{
            value:""
        }
    }
}
</script>