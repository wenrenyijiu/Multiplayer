<template>
  <div style="height: 100%;width:100%;border:1.5px solid lightgray;" class="div">
        <!-- //VisMultilayer -->
        <div style="display: flex;align-items: center;height: 5%;width: 100%;background-color: lightskyblue;">
            <div>
                <span style="font-size: 18px;font-weight: 700;margin-left: 10px;">
                    VisMultilayer
                </span>
            </div>
        </div>

        <!-- //file等 -->
        <div style="display: flex;align-items: center;height: 5%;width: 100%;border: 1px solid lightgray;background-color:#F5F5F5;">
            <span style="font-weight: 500;margin-left: 10px;">File</span>
            <span style="margin-left: 40px;font-weight: 500;">Layout</span>
            <span style="margin-left: 40px;font-weight: 500;">About</span>
  
        </div>

        <!-- //放大、缩小、控制区等 -->
        <div style="padding: 10px;width: 330px;border:1.5px solid lightgray;height: 87.3%;">
            <!-- 图标区 -->
            <img src="./放大.png" style="height: 20px;"  alt="上海鲜花港 - 郁金香" />
            <img src="./缩小.png" style="height: 20px;margin-left: 40px;"  alt="上海鲜花港 - 郁金香" />
            <img src="./刷新.png" style="height: 20px;margin-left: 40px;"  alt="上海鲜花港 - 郁金香" />
            <img src="./quanping.png" style="height: 20px;margin-left: 40px;"  alt="上海鲜花港 - 郁金香" />

            <!-- Control panel -->
             <div style="margin-top: 10px;display:flex;justify-content: flex-start;align-items: center;">
                <div style="background-color: lightgray;border:1px solid lightgray;height: 1px;width: 40px;"></div>
                <!-- <hr style="margin-left:0;width: 10px;height: 1px;margin-right: 3px;background-color:lightgray ;"/> -->
                <span style="font-size: 16px;font-weight: 700;display: block;margin: 10px;">Control panel</span>
                <div style="background-color: lightgray;border:1px solid lightgray;height: 1px;width: 140px;"></div>
                <!-- <hr style="margin-left:10px;width: 115px;height: 1px;margin-right: 3px;background-color:lightgray ;"/> -->
             </div>
             <div style="display: flex;justify-content: space-around;margin-top: 20px;">
                <div style="width: 120px;border: 1px solid lightgray;height: 238px;"></div>
                <div style="width: 120px;border: 1px solid lightgray;height: 238px"></div>
            </div>

            <!-- Node information -->
             <div style="margin-top: 20px;display:flex;justify-content: flex-start;">
                <hr style="margin-left:0;width: 10px;height: 1px;margin-right: 3px;background-color:lightgray ;"/>
                <span style="font-size: 16px;font-weight: 700;">Node information</span>
                <hr style="margin-left:10px;width: 80px;height: 1px;margin-right: 3px;background-color:lightgray ;"/>
             </div>
             <div style="display: flex;justify-content: space-around;margin-top: 20px;">
                 <div style="width: 84px;border: 1px solid lightgray;height: 238px;"></div>
                 <div style="width: 84px;border: 1px solid lightgray;height: 238px"></div>
                 <div style="width: 84px;border: 1px solid lightgray;height: 238px"></div>
             </div>
        </div>

    </div>
</template>

<script>
export default {
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
</style>
