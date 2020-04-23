<template>
  <el-container class="home-container">
    <!-- 头部区域 -->
    <el-header>
      <div class="iconfont">
        <img src="../assets/multilayer.png" style="height: 15px;margin-right:7px" alt="上海鲜花港 - 郁金香" />
        <span style="font-size: 18px;font-weight: 700;">VisMultilayer</span>
      </div>
      <div style="height:1px;width:100%;background-color:white;margin-left:10px;margin-top:5px"></div>
      <div class="file">
        <!-- <button> -->
        <span style="font-weight: 500;font-size:14px;margin-left: 6px;">File</span>
        <span style="font-weight: 500;font-size:14px;margin-left: 40px;">Layout</span>
        <span style="font-weight: 500;font-size:14px;margin-left: 40px;">Select</span>
        <span style="font-weight: 500;font-size:14px;margin-left: 40px;">About</span>
        <!-- </button> -->
      </div>
    </el-header>
    <!-- 页面主体区域 -->
    <el-container>
      <!-- 侧边栏 -->
      <el-aside>
        <!-- //放大、缩小、控制区等 -->
        <!-- 图标区 -->
        <div class="myfont">
          <img src="../assets/放大.png" style="height: 27px;" alt="上海鲜花港 - 郁金香" />
          <img src="../assets/缩小.png" style="height: 27px;margin-left: 40px;" alt="上海鲜花港 - 郁金香" />
          <img src="../assets/刷新.png" style="height: 25px;margin-left: 40px;" alt="上海鲜花港 - 郁金香" />
          <img
            src="../assets/quanping.png"
            style="height: 27px;margin-left: 40px;"
            alt="上海鲜花港 - 郁金香"
          />
        </div>
        <!-- Control panel -->
        <div style="display:flex;justify-content: flex-start;align-items: center;">
          <div
            style="background-color: black;border:1px solid lightgray;height: 1px;width: 75px;margin-left:5px"
          ></div>
          <!-- <hr style="margin-left:0;width: 10px;height: 1px;margin-right: 3px;background-color:lightgray ;"/> -->
          <span style="font-size: 16px;font-weight: 700;display: block;margin: 10px;">Control panel</span>
          <div style="background-color: black;border:1px solid lightgray;height: 1px;width: 75px;"></div>
          <!-- <hr style="margin-left:10px;width: 115px;height: 1px;margin-right: 3px;background-color:lightgray ;"/> -->
        </div>

        <!-- <el-radio-group v-model="radio">
          <el-radio :label="3">All</el-radio>
          <el-radio :label="6">1/2</el-radio>
          <el-radio :label="9">1/4</el-radio>
        </el-radio-group>-->

        <div style="margin-top: 10px;">
          <!-- <el-select v-model="value" filterable placeholder="选择时间区间" size="small">
            <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
            ></el-option>
          </el-select>-->
          <!-- <div style="width: 240px;border: 1px solid lightgray;height: 160px;margin:10px 10px"> -->

          <!-- </div> -->
          <!-- <div style="width: 120px;border: 1px solid lightgray;height: 200px"></div> -->
        </div>
        <!-- 密度 -->
        <div style="text-align:center;margin-left:5px;">
          <div style="margin:10px">
            <span>选择时间区间</span>
            <el-date-picker
              size="mini"
              v-model="value1"
              type="daterange"
              range-separator="至"
              start-placeholder="开始日期"
              end-placeholder="结束日期"
              style="width:80%;margin-top:10px"
            ></el-date-picker>
          </div>
          <div style="display:flex;justify-content:center;align-items: center">
            <div>
              <el-button
                type="primary"
                plain
                style="margin-top:10px;height:40px;margin-bottom:20px "
                size="small"
              >Generate network</el-button>

              <el-checkbox-group size="mini" v-model="checkList">
                <el-checkbox size="mini" label="1/2 multilayer"></el-checkbox>
                <el-checkbox label="All multilayer"></el-checkbox>
              </el-checkbox-group>
            </div>
          </div>
        </div>
        <!-- 按钮 -->
        <!-- Node information -->
        <div style="margin-top: 10px;display:flex;justify-content: flex-start;align-items: center;">
          <div
            style="margin-left:5px;background-color: black;border:1px solid lightgray;height: 1px;width: 60px;"
          ></div>
          <span style="font-size: 16px;font-weight: 700;margin: 10px;">Node information</span>
          <div style="background-color: black;border:1px solid lightgray;height: 1px;width: 60px;"></div>
        </div>
        <div class="myspan" style="display: flex;justify-content: space-around;">
          <span>overview</span>
          <span>subview</span>
          <span>detailview</span>
        </div>
        <div style="display: flex;justify-content: space-around;margin-top:6px">
          <div style="width: 84px;border: 1px solid lightgray;height: 170px;"></div>
          <div style="width: 84px;border: 1px solid lightgray;height: 170px"></div>
          <div style="width: 84px;border: 1px solid lightgray;height: 170px"></div>
        </div>
        <el-checkbox-group size="mini" v-model="checkList" style="margin-top:20px">
          <el-checkbox size="mini" label="lock node"></el-checkbox>
        </el-checkbox-group>
      </el-aside>
      <!-- 右侧内容主体 -->
      <el-main>
        <el-row style="margin-left:10px;margin-right:10px;margin-bottom:0">
          <el-col :span="24">
            <div
              style="background-color:white;border-radius: 10px;display:flex;justify-content: flex-start;align-items: flex-start;"
            >
              <div class="img-ra">
                <img
                  src="../assets/KHCFDC_旋转.png"
                  alt="上海鲜花港 - 郁金香"
                  style="height:20px;margin:0 10px 0 10px "
                />
                <span>Rotate direction</span>
              </div>
              <img
                src="../assets/vismul.png"
                alt="上海鲜花港 - 郁金香"
                style="height:320px;margin-right:30px"
              />
              <div class="myslider">
                <span style="display:block;margin-left:30px">Select network density</span>
                <el-slider v-model="value" range :marks="marks" vertical height="250px"></el-slider>
              </div>
            </div>
          </el-col>
        </el-row>
        <div style="background-color:#4169E1;border-radius: 10px;display:flex;margin:10px 0 0 10px">
          <div style="border-radius: 10px;height:390px;background-color:white;">
            <img src="../assets/over-institute.png" alt="上海鲜花港 - 郁金香" />
          </div>
          <div
            style="border-radius: 10px;margin:0 10px 0 10px;height:390px;background-color:white;"
          >
            <img src="../assets/sub-institute.png" alt="上海鲜花港 - 郁金香" />
          </div>
          <div style="border-radius: 10px;height:390px;background-color:white;">
            <img src="../assets/institute-tetail.png" alt="上海鲜花港 - 郁金香" />
          </div>
        </div>

        <!-- <el-row style="margin-left:10px;margin-right:10px;margin-top:10px;">
          <el-col :span="24">
            
          </el-col>
        </el-row>-->
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  data() {
    return {
      pickerOptions: {
        shortcuts: [
          {
            text: "最近一周",
            onClick(picker) {
              const end = new Date();
              const start = new Date();
              start.setTime(start.getTime() - 3600 * 1000 * 24 * 7);
              picker.$emit("pick", [start, end]);
            }
          },
          {
            text: "最近一个月",
            onClick(picker) {
              const end = new Date();
              const start = new Date();
              start.setTime(start.getTime() - 3600 * 1000 * 24 * 30);
              picker.$emit("pick", [start, end]);
            }
          },
          {
            text: "最近三个月",
            onClick(picker) {
              const end = new Date();
              const start = new Date();
              start.setTime(start.getTime() - 3600 * 1000 * 24 * 90);
              picker.$emit("pick", [start, end]);
            }
          }
        ]
      },
      value1: "",
      value2: "",
      checkList: ["选中且禁用", "复选框 A"],
      value: [50, 50],
      marks: {
        0: "none",
        25: "25% density",
        75: "75% density",
        50: {
          style: {
            color: "#1989FA"
          },
          label: this.$createElement("strong", "50% density")
        }
      }
    };
  },
  created() {},
  methods: {}
};
</script>

<style scoped>
.home-container {
  height: 100%;
  background-color: #4169e1;
}

.iconfont {
  margin-top: 8px;
  margin-left: 10px;
}

.el-header {
  text-align: left;
  padding-left: 0;
  align-items: center;
  color: #fff;
  font-size: 20px;
  height: 70px !important;

  > div {
    display: flex;
    align-items: center;
    span {
      margin-left: 15px;
    }
  }
}

.file {
  margin-top: 2px;
  margin-left: 10px;
}
.el-aside {
  background-color: white;
  width: 330px !important;
  border-radius: 10px;
  margin: 0 0 20px 10px;
}

.el-main {
  background-color: #4169e1;
  padding: 0;
}

.el-main img {
  height: 326px;

  margin-top: 20px;
  border-radius: 10px;
}

.el-mainimg {
  height: 310px;

  margin-top: 20px;
}

.iconfont {
  margin-right: 10px;
}

.toggle-button {
  background-color: #4a5064;
  font-size: 10px;
  line-height: 24px;
  color: #fff;
  text-align: center;
  letter-spacing: 0.2em;
  cursor: pointer;
}

.body {
  width: 100%;
  height: 100%;
  background-color: #f5f5f5;
  display: flex;
}

.control {
  padding: 10px;
  width: 100%;

  height: 100%;
  border-radius: 7px;
  background-color: #fff;
}

.myfont {
  margin-top: 10px;
  padding-left: 5px;
  text-align: left;
}

/* .view{
  margin: 10px;
  margin-left: 0;
  padding: 10px;
  width: 75%;
  border:1.5px solid lightgray;
  height: 650px;
  border-radius: 7px;
  background-color: #fff;
} */
.myview {
  height: 660px;
  width: 100%;
  background-color: #f5f5f5;
  margin-top: 10px;
  display: flex;
}

.mul-over {
  width: 440px;
  height: 670px;
  background-color: #f5f5f5;

  border-radius: 7px;
}

.mulview {
  width: 440px;
  height: 330px;
  background-color: white;
  border-radius: 7px;
}

.overview {
  width: 440px;
  height: 330px;
  background-color: white;
  margin-top: 10px;
  border-radius: 7px;
}

.sub-de {
  width: 380px;
  height: 670px;
  background-color: white;

  border-radius: 7px;
  margin-left: 10px;
}

.layer {
  width: 100%;
  height: 360px;
  background-color: #f5f5f5;
  display: flex;
}

.multiplar {
  height: 350px;
  width: 480px;
  background-color: #fff;
  border-radius: 7px;
}
.myview img {
  height: 260px;

  margin-top: 10px;
}

.subview {
  height: 350px;
  width: 480px;
  background-color: #fff;
  border-radius: 7px;
}

.detail {
  margin-left: 10px;
  height: 350px;
  width: 420px;
  background-color: #fff;
  border-radius: 7px;
}

button {
  border: 1px solid #f5f5f5;
}

.myspan span {
  font-size: 12px;
  font-weight: 530;
  margin-top: 30px;
}

.el-row {
  margin: 0;
  padding: 0;
  &:last-child {
    margin-bottom: 0;
  }
}
.el-col {
  border-radius: 4px;
  margin: 0;
  padding: 0;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  background: #d3dce6;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
.row-bg {
  padding: 0;
  background-color: #f9fafc;
}

.img-ra {
  display: flex;
  align-items: center;
  margin: 40px 20px 0 20px;
}

.myslider {
  margin-top: 50px;
}
</style>
