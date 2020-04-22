<template>
  <div style="height: 100%;width:100%;border:1.5px solid lightgray;background-color:#F5F5F5;">
    <!-- //VisMultilayer -->
    <div
      style="display: flex;align-items: center;height: 5%;width: 100%;background-color: lightskyblue;"
    >
      <div style="margin-left:10px">
        <img src="../assets/多层结构.png" style="height: 15px;margin-right:7px" alt="上海鲜花港 - 郁金香" />
        <span style="font-size: 18px;font-weight: 700;">VisMultilayer</span>
      </div>
    </div>

    <!-- //file等 -->
    <div
      style="display: flex;align-items: center;height: 5%;width: 100%;border: 1px solid lightgray;background-color:#F5F5F5;"
    >
      <button>
        <span style="font-weight: 600;margin-left: 10px;">File</span>
      </button>
      <button>
        <span style="margin-left: 40px;font-weight: 600;">Layout</span>
      </button>
      <button>
        <span style="margin-left: 40px;font-weight: 600;">About</span>
      </button>
    </div>

    <!-- 主体控制面板视图区 -->
    <div class="body">
      <!-- //放大、缩小、控制区等 -->
      <div class="control">
        <!-- 图标区 -->
        <div class="myfont">
          <img src="../assets/放大.png" style="height: 20px;" alt="上海鲜花港 - 郁金香" />
          <img src="../assets/缩小.png" style="height: 20px;margin-left: 40px;" alt="上海鲜花港 - 郁金香" />
          <img src="../assets/刷新.png" style="height: 20px;margin-left: 40px;" alt="上海鲜花港 - 郁金香" />
          <img
            src="../assets/quanping.png"
            style="height: 20px;margin-left: 40px;"
            alt="上海鲜花港 - 郁金香"
          />
        </div>
        <!-- Control panel -->
        <div style="margin-top: 10px;display:flex;justify-content: flex-start;align-items: center;">
          <div
            style="background-color: lightgray;border:1px solid lightgray;height: 1px;width: 30px;"
          ></div>
          <!-- <hr style="margin-left:0;width: 10px;height: 1px;margin-right: 3px;background-color:lightgray ;"/> -->
          <span style="font-size: 16px;font-weight: 700;display: block;margin: 10px;">Control panel</span>
          <div
            style="background-color: lightgray;border:1px solid lightgray;height: 1px;width: 50px;"
          ></div>
          <!-- <hr style="margin-left:10px;width: 115px;height: 1px;margin-right: 3px;background-color:lightgray ;"/> -->
        </div>
        <!-- <el-radio-group v-model="radio">
          <el-radio :label="3">All</el-radio>
          <el-radio :label="6">1/2</el-radio>
          <el-radio :label="9">1/4</el-radio>
        </el-radio-group>-->
        <el-checkbox-group size="mini" v-model="checkList">
          <el-checkbox size="mini" label="All multilayer"></el-checkbox>
          <el-checkbox size="mini" label="1/2 multilayer" style="margin-left:5px;"></el-checkbox>
        </el-checkbox-group>
        <div style="margin-top: 10px;">
          <el-select v-model="value" filterable placeholder="选择时间区间" size="small">
              <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value">
              </el-option>
            </el-select>
          <div style="width: 240px;border: 1px solid lightgray;height: 160px;margin:10px 10px">
            
          </div>
          <!-- <div style="width: 120px;border: 1px solid lightgray;height: 200px"></div> -->
        </div>
        <!-- 密度 -->
        <div style="margin-top:10px">
          <span style="font-size:12px;text-align:left;">Multilayer network density</span>
          <el-slider v-model="value5" disabled style="height:30px"></el-slider>
        </div>
        <!-- 按钮 -->
        <el-button
          type="info"
          plain
          style="margin-top:10px;border:1px solid lightgray; "
          size="small"
        >Generate network</el-button>

        <!-- Node information -->
        <div style="margin-top: 10px;display:flex;justify-content: flex-start;align-items: center;">
          <div
            style="background-color: lightgray;border:1px solid lightgray;height: 1px;width: 30px;"
          ></div>
          <span style="font-size: 16px;font-weight: 700;margin: 10px;">Node information</span>
          <div
            style="background-color: lightgray;border:1px solid lightgray;height: 1px;width: 50px;"
          ></div>
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
      </div>

      <!-- 视图区 -->
      <div class="myview">
        <div class="mul-over">
          <div class="mulview">
            <img src="../assets/多层.png" alt="上海鲜花港 - 郁金香" style="height:300px" />
          </div>
          <div class="overview">
            <img src="../assets/over-institute.png" alt="上海鲜花港 - 郁金香" />
          </div>
        </div>
        <div class="sub-de">
          <img src="../assets/sub-institute.png" alt="上海鲜花港 - 郁金香" />
          <img src="../assets/detail.png" alt="上海鲜花港 - 郁金香" />
        </div>
        <!-- <div class="layer">
          <div class="multiplar">
            <img src="../assets/多层.png" alt="上海鲜花港 - 郁金香" />
          </div>
          <div class="overview">
            <img src="../assets/sub-institute.png" alt="上海鲜花港 - 郁金香" />
          </div>
        </div>
        <div class="mulview">
          <div class="subview">
            <img src="../assets/over-institute.png" alt="上海鲜花港 - 郁金香" />
          </div>
          <div class="detail">
            <img src="../assets/detail.png" alt="上海鲜花港 - 郁金香" />
          </div>
        </div>-->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      checkList: ["选中且禁用", "复选框 A"],
      value5: 42
    };
  },
  name: "HelloWorld",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
html,
body,
.div {
  height: 100%;
  width: 100%;
  min-width: 1000px;
}

.myfont {
  display: flex;
  justify-content: flex-start;
}

.body {
  width: 100%;
  height: 700px;
  background-color: #f5f5f5;
  display: flex;
  
}

.control {
  margin: 10px;
  padding: 10px;
  width: 24%;

  height: 660px;
  border-radius: 7px;
  background-color: #fff;
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
  height: 310px;

  margin-top: 20px;
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
}
</style>
