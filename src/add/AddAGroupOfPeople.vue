<template>
  <div id="AddAGroupOfPeople">
    <div class="header">
      <div class="header-1">
        <span>创建活动</span>
      </div>
    </div>
    <div class="title">
      <div class="title-1">
        <div class="title-a title-img">
          <span>基本信息</span>
        </div>
        <div class="title-b">
          <el-form
            :model="ruleForm"
            :rules="rules"
            ref="ruleForm"
            label-width="100px"
            class="demo-ruleForm"
          >
            <el-form-item label="活动名称" prop="name">
              <el-input v-model="ruleForm.name"></el-input>
            </el-form-item>
            <el-form-item label="活动时间" required>
              <el-col :span="11">
                <el-form-item prop="date1">
                  <el-date-picker
                    type="date"
                    placeholder="选择日期"
                    v-model="ruleForm.date1"
                    style="width: 100%;"
                  ></el-date-picker>
                </el-form-item>
              </el-col>
              <el-col class="line" :span="2">至</el-col>
              <el-col :span="11">
                <el-form-item prop="date2">
                  <el-date-picker
                    type="date"
                    placeholder="选择日期"
                    v-model="ruleForm.date2"
                    style="width: 100%;"
                  ></el-date-picker>
                </el-form-item>
              </el-col>
            </el-form-item>
            <el-form-item label="团有效期">
              <el-select v-model="ruleForm.region" placeholder="1" class="input-select">
                <el-option label="1" value="1"></el-option>
                <el-option label="2" value="2"></el-option>
                <el-option label="3" value="3"></el-option>
              </el-select>
              <span>天</span>
              <el-select v-model="ruleForm.region" placeholder="1" class="input-select">
                <el-option label="1" value="4"></el-option>
                <el-option label="2" value="5"></el-option>
                <el-option label="3" value="6"></el-option>
              </el-select>
              <span>时</span>
              <el-select v-model="ruleForm.region" placeholder="1" class="input-select">
                <el-option label="1" value="7"></el-option>
                <el-option label="2" value="8"></el-option>
                <el-option label="3" value="9"></el-option>
              </el-select>
              <span>分</span>
            </el-form-item>
            <el-form-item label="参团限制" prop="resource">
              <el-radio-group v-model="ruleForm.resource">
                <el-radio label="所有用户均可参团"></el-radio>
                <el-radio label="仅限新用户"></el-radio>
              </el-radio-group>
            </el-form-item>
            <el-form-item label="活动限制" prop="resource">
              <el-radio-group v-model="ruleForm.resource">
                <el-radio label="不限"></el-radio>
                <el-radio label="限购"></el-radio>
              </el-radio-group>
            </el-form-item>
            <el-form-item label="活动课程">
              <el-select v-model="ruleForm.region" placeholder="选择课程" class="input-select">
                <el-option label="课程1" value="one"></el-option>
                <el-option label="课程2" value="two"></el-option>
              </el-select>
              <br />
              <span class="span">请选择要参加拼团的商品，一旦参加活动，该商品在活动期间不可修改。</span>
            </el-form-item>
            <el-form-item label="活动价格" prop="pice">
              <el-input v-model="ruleForm.pice"></el-input>
            </el-form-item>
          </el-form>
        </div>
      </div>
      <div class="title-1">
        <div class="title-a title-img">
          <span>更多设置</span>
        </div>
        <div class="title-b">
          <el-form
            :model="ruleForm"
            :rules="rules"
            ref="ruleForm"
            label-width="100px"
            class="demo-ruleForm"
          >
            <el-form-item label="凑团" prop="ct">
              <el-switch v-model="ruleForm.ct"></el-switch>
            </el-form-item>
            <p class="span1">开启凑团后，对于未参团的买家，活动商品详情页会显示待成团的团列表，买家可以直接任选一个参团，提升成团率。</p>
            <el-form-item label="模拟成团" prop="mnct">
              <el-switch v-model="ruleForm.mnct"></el-switch>
            </el-form-item>
            <br/>
            <p class="span1">开启模拟成团后，该团有效期结束时，人数未满的团，系统将会模拟“匿名买家”凑满人数，使该团成团。只有已付款参团的真实买家才会获得商品，建议合理开启，以提高成团率。</p>
            <el-form-item label="团长优惠" prop="tzyh">
              <el-switch v-model="ruleForm.tzyh"></el-switch>
            </el-form-item>
            <br/>
            <p class="span1">开启团长(开团人)优惠后，团长将享受更优惠价格，有助于提高开团率和成团率。请注意：模拟成团的团长也能享受团长优惠，请谨慎设置，避免资金损失。</p>
            <el-form-item label="阶梯价" prop="jtj">
              <el-switch v-model="ruleForm.jtj"></el-switch>
            </el-form-item>
            <br/>
            <p class="span1">开启阶梯价后，可根据不同的参团人数设置不同的拼团价格，人数越多价格越低，刺激用户发起人数更多的拼团。</p>
            <el-form-item label="参团人数展示" prop="ctrszs">
              <el-switch v-model="ruleForm.ctrszs"></el-switch>
            </el-form-item>
            <br/>
            <p class="span1">开启展示后，拼团页面将展示“已有xx人参团”，参团人数为设定人数和实际参团人数之和，实时更新。</p>
            <el-form-item>
              <el-button type="primary" @click="to">提交</el-button>
            </el-form-item>
          </el-form>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "AddAGroupOfPeople",
  data() {
    return {
      value: true,
      formInline: {
        user: "",
        region: ""
      },
      ruleForm: {
        name: "",
        primary: "",
        section: "",
        lecturer: "",
        type: "",
        freeadmission: false
      },
      rules: {
        name: [{ required: true, message: "请输入活动名称", trigger: "blur" }],
        pice: [{ required: true, message: "请输入活动价格", trigger: "blur" }]
      }
    };
  },
  methods: {
    to() {
      this.$router.push({
        path: "agroupofpeople"
      });
    },
    submitForm(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          alert("submit!");
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  }
};
</script>
<style scoped>
#AddAGroupOfPeople {
  margin-top: 20px;
  background: #f2f2f2;
}
.span1{
  margin: -20px 0 10px 100px;
}
.span,.span1{
  font-size: 12px;
  color: dimgray;
}
.title-a,
.title-b {
  margin-left: 20px;
  float: left;
}
.title-a {
  margin-top: 40px;
}
.title-b img {
  width: 89%;
  margin-top: -50px;
  margin-left: 150px;
}
.title-img > span {
  padding: 20px 42px;
  background: url("../../img/3.png") no-repeat;
}
.header {
  background: #fff;
  width: 95%;
  margin: 20px 0 20px 50px;
}
.header-1 {
  font-size: 13px;
  text-align: left;
  padding: 20px;
}
.title {
  clear: both;
  background: #fff;
  width: 95%;
  height: 92%;
  margin: 20px 0 0px 50px;
}
.title-1 {
  clear: both;
  margin: 20px 0 0 50px;
  padding-top: 20px;
  width: 91%;
}
.input-select {
  width: 28%;
}
.title-b {
  width: 50%;
}
</style>