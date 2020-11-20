<template>
  <div>
    <div class="daohan">
      <p>页面导航</p>
      <p>头像</p>
      <p>admin 退出</p>
    </div>
    <div class="qb">
      <div class="biaoti">
        <p>课程详情</p>
        <p>返回</p>
      </div>
        <div class="jbxx">
        <p>基本信息</p>
    </div>
    <template>
      <el-table :data="tableData" height="97" border style="width: 90%" class="biao1">
        <el-table-column prop="date" label="课程ID" width="180"></el-table-column>
        <el-table-column prop="name" label="课程名称" width="180"></el-table-column>
        <el-table-column prop="address" label="课程图片" width="127px">
              <template>
            <img src="../img/tu2.png" width="40px"/>
          </template>
        </el-table-column>
        <el-table-column prop="address2" label="课程时长" width="200"></el-table-column>
        <el-table-column prop="address3" label="课程章节"></el-table-column>
      </el-table>
    </template>
        <template>
      <el-table :data="tableData" height="97" border style="width: 90%" class="biao2">
        <el-table-column prop="date1" label="讲师" width="180"></el-table-column>
        <el-table-column prop="name1" label="课程类型" width="180"></el-table-column>
        <el-table-column prop="address1" label="在学人数">
        </el-table-column>
        <el-table-column prop="address4" label="添加时间" width="200"></el-table-column>
        <el-table-column prop="address5" label="学员QQ交流群"></el-table-column>
      </el-table>
    </template>
        <div class="jbxx">
        <p>课程介绍</p>
    </div>
    <div>
       <el-form>
           <el-form-item>
           <el-input type="textarea" v-model="a" class="in1"></el-input>
       </el-form-item>
       </el-form>
    </div>
        <div class="jbxx">
        <p>讲师介绍</p>
    </div>
    <div class="jiangshi">
        <p><span class="yans">*</span>讲师头像：<img src="../img/tu7.png" width="40px" class="jiangshit"></p>
        <p><span class="yans">*</span>讲师姓名：<span class="jsxm">王昭君</span></p>
        <p><span class="yans">*</span>讲师介绍：<span class="jsxm">
            介绍介绍，，，，，，，，，，，所有作业和实战，我们学员1对1批改；不是简单的打分式批<br></span>
            <span class="duanl1">是详细的逐行代码批改所作业和实战，我们学员1对1批改；不是简单的打分式批改，是详细的<br></span>
             <span class="duanl1">逐行代码批改，所作业和实战，我们学员1对1批改；不是简单的打分式批改，是详细的逐行代<br></span>
            <span class="duanl1"> 码批改，所有作业和战，我们学员1对1批改；不是简单的打分式批改，是详细的逐行代码批.</span>
            </p>
    </div>
       <div class="kcsp">
        <p>课程视频</p>
    </div>
    <div class="kctp">
        <img src="../img/tu8.png" width="800px">
    </div>
    <div class="jbxx">
        <p>课程章节</p>
    </div>
    <div>
        <el-collapse v-model="activeNames" @change="handleChange" class="xiala">
  <el-collapse-item title="一致性 Consistency" name="1">
    <div>与现实生活一致：与现实生活的流程、逻辑保持一致，遵循用户习惯的语言和概念；</div>
    <div>在界面中一致：所有的元素和结构需保持一致，比如：设计样式、图标和文本、元素的位置等。</div>
  </el-collapse-item>
  <el-collapse-item title="反馈 Feedback" name="2">
    <div>控制反馈：通过界面样式和交互动效让用户可以清晰的感知自己的操作；</div>
    <div>页面反馈：操作后，通过页面元素的变化清晰地展现当前状态。</div>
  </el-collapse-item>
  <el-collapse-item title="效率 Efficiency" name="3">
    <div>简化流程：设计简洁直观的操作流程；</div>
    <div>清晰明确：语言表达清晰且表意明确，让用户快速理解进而作出决策；</div>
    <div>帮助用户识别：界面简单直白，让用户快速识别而非回忆，减少用户记忆负担。</div>
  </el-collapse-item>
  <el-collapse-item title="可控 Controllability" name="4">
    <div>用户决策：根据场景可给予用户操作建议或安全提示，但不能代替用户进行决策；</div>
    <div>结果可控：用户可以自由的进行操作，包括撤销、回退和终止当前操作等。</div>
  </el-collapse-item>
</el-collapse>
    </div>
  </div>
</div>
</template>

<style>
* {
  padding: 0;
  margin: 0;
}
.daohan {
  width: 100%;
  height: 80px;
  background: white;
  position: fixed;
  top: -1px;
  z-index: 9;
}
.daohan > p:nth-of-type(1) {
  float: left;
  text-indent: 20px;
  line-height: 80px;
  color: #9f9f9f;
}
.daohan > p:nth-of-type(2) {
  border: 1px solid #d0d0d0;
  width: 40px;
  height: 40px;
  margin-left: 700px;
  text-align: center;
  line-height: 40px;
  border-radius: 50%;
  color: white;
  background: #d0d0d0;
  margin-top: 25px;
}
.daohan > p:nth-of-type(3) {
  margin-left: 370px;
  margin-top: -30px;
}
.qb {
  width: 100%;
  height: 2000px;
  background: white;
  margin-top: 100px;
}
.biaoti {
  height: 40px;
  border-bottom: 1px solid #f2f2f2;
}
.biaoti > p:nth-of-type(1) {
  float: left;
  margin-left: 20px;
  line-height: 40px;
}
.biaoti > p:nth-of-type(2) {
  float: right;
  margin-right: 20px;
  line-height: 25px;
  font-size: 13px;
  border: 1px solid gainsboro;
  width: 50px;
  height: 25px;
  margin-top: 8px;
  cursor: pointer;
}
.biao1 {
    margin-top: 45px;
  margin-left: 45px;
}
.biao2{
    margin-left: 45px;
}
.jbxx>p:nth-of-type(1){
    border-left: 3px solid #128fe9;
    width: 80px;
    margin-left:45px;
    margin-top: 40px;
}
.in1{
     width: 800px;
     margin-top: 40px;
}
.el-textarea__inner{
       height: 200px;
}
.yans{
    color: red;
}
.jiangshi>p:nth-of-type(1){
    float: left;
    margin-top: 30px;
    margin-left: 45px;
}
.jiangshit{
    margin-left: 40px;
    position: relative;
    top: 10px;
}
.jiangshi>p:nth-of-type(2){
   float: left;
   margin-top: 130px;
   margin-left: -168px;
}
.jsxm{
    margin-left: 40px;
}
.jiangshi>p:nth-of-type(3){
   float: left;
   margin-top: 40px;
   margin-left: 45px;
}
.duanl1{
    margin-left: 125px;
}
.kcsp>p:nth-of-type(1){
      border-left: 3px solid #128fe9;
    width: 80px;
    margin-left:45px;
    margin-top:330px;
}
.kctp>img{
    margin-top: 40px;
}
.xiala{
    width: 800px;
    margin-left: 45px;
    margin-top: 45px;
}
</style>
<script>
export default {
    data() {
      return {
          a:"介绍介绍介绍，这是内容内容内容，，，，，，所有作业和实战，我们针每一位学员1对1批改；不是简单的打分式批改，是详细的逐行代码批改所有作业和实战，我们针对每一位学员1对1批改；不是简单的打分式批改，是详细的逐行代码批改，所有作业和实战，我们针对每一位学员1对1批改；不是简单的打分式批改，是详细的逐行代码批改，所有作业和实战，我们针对每一位学员1对1批改；不是简单的打分式批改，是详细的逐行代码批改。。腾讯爱奇艺修改超前点播规则你怎么看，个人感觉这纯粹是换汤不换药，感觉付费比之前更多了，每次更新都 要花3块，18元买六集，除非脑子不清楚才会花钱买吧",
        tableData: [{
          date: '20190909120909',
          name:'教学观',
          address2: '20小时',
          address3: '98小节',
           date1: '王昭君',
          name1:'综合素质',
          address1: '123',
          address4: '2017-07-19 14:48:38',
          address5: '1234444444'
        }]
      }
    }
  }
</script>