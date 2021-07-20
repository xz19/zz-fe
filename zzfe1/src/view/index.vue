<template>
  <div class="box">
    <p class="box-p">
    <el-select class="box-bor" v-model="value" placeholder="请选择">
      <el-option v-for="item in options" :key="item.value" :value="item.value">
      </el-option>
    </el-select>
    <el-select class="box-bor" v-model="bol" placeholder="请选择">
      <el-option v-for="i in symbol" :key="i.bol" :value="i.bol"> </el-option>
    </el-select>
    <el-select class="box-bor" v-model="vle" placeholder="请选择">
      <el-option v-for="item in option" :key="item.vle" :value="item.vle">
      </el-option>
    </el-select>
    <el-button type="primary" class="box-but" @click="bandleclick">执行</el-button>
    </p>
    <el-button disabled class="box-text" v-model="res">
      <span class="box-result">执行结果：</span> 
      <span class="box-res">{{res}}</span>
    </el-button>
  </div>
  
</template>
<script>
export default {
  name: "Index",
  data() {
    return {
      options: [
        {
          value: "2",
        },
        {
          value: "4",
        },
        {
          value: "8",
        },
        {
          value: "16",
        },
        {
          value: "32",
        },
        {
          value: "64",
        },
        {
          value: "1024",
        },
      ],
      symbol: [
        {
          bol: "+",
        },
        {
          bol: "-",
        },
        {
          bol: "*",
        },
        {
          bol: "/",
        },
      ],
      option: [
        {
          vle: "1",
        },
        {
          vle: "2",
        },
        {
          vle: "3",
        },
        {
          vle: "4",
        },
        {
          vle: "5",
        },
        {
          vle: "99",
        },
        {
          vle: "100",
        },
      ],
      value: "",
      bol: "",
      vle: "",
      res: "",
    };
  },
  methods: {
    bandleclick: function () {
      if (this.value != null && this.vle != null) {
        switch (this.bol) {
          case "+":
            this.res = parseInt(this.value) + parseInt(this.vle);
            break;
          case "*":
            this.res = parseInt(this.value) * parseInt(this.vle);
            break;
          case "-":
            this.res = parseInt(this.value) - parseInt(this.vle);
            break;
          case "/":
            this.res = parseInt(this.value) / parseInt(this.vle);
            break;
        }
      }
    //   console.log(this.res);
    },
  },
};
</script>
<style scoped>
.box {
  position: absolute;
  width: 910px;
  height: 330px;
  left: 271px;
  top: 174px;

  background: #f2f2f2;
}
.box-p{
    margin: 40px 0 52px 43px;
}
.box-bor {
  width: 224px;
  height: 40px;
  margin-left: 9px;
}
.box-but {
  width: 121px;
  height: 40px;
  margin-left: 9px;
}
.box-text {
  position: absolute;
  top: 0px;
  left: 50%;
  min-width: 457px;
  height: 150px;
  transform: translate(-50%);
  box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.1);
  border-radius: 12px;
  padding: 0;
  position: relative;
}
.box-result{
  color: #888888;
  font-size: 25px;
  margin-left: 41px;
  width: 125px;
  vertical-align: middle;
}
.box-res{
  font-size: 91px;
  margin-left: 37px;
  color: black;
  vertical-align: middle;
  margin-right: 35px;
}
</style>
