<template>
  <div>
    <div id="header">普通的演示</div>
    <div id="container1">
      这是一个普通的演示。在head头加载hotcss.js。 优雅的使用scss书写css。单位均使用了px2rem处理
    </div>
    <div id="container2">
      这个里面的字体没有使用px2rem。具体写法参看css。 如果你在使用chrome。请打开控制台，尝试模拟不同设备，来查看表现。
    </div>
  </div>
</template>

<script>
export default {
  name: 'Test',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import 'px2rem'; //第一步先把px2rem导入
$designWidth: 750; //写scss之前，必须要先定义designWidth。 设计稿尺寸

#header {
  width: px2rem(750);
  height: px2rem(88);
  line-height: px2rem(88);
  background-color: #33aa33;
  text-align: center;
  font-size: px2rem(48);
  color: rgba(255, 255, 255, 1);
}

#container1 {
  margin-top: px2rem(10);
  padding: px2rem(30);
  background-color: #191919;
  color: #f0f0f0;
  line-height: 1.7;
  max-height: 100%;
  font-size: px2rem(32);
}

// 根据dpr适配px值
#container2 {
  margin-top: px2rem(10);
  padding: px2rem(30);
  background-color: #191919;
  color: #f0f0f0;
  line-height: 1.7;
  max-height: 100%;
  font-size: 12px;
  [data-dpr='2'] & {
    font-size: 24px;
  }
  [data-dpr='3'] & {
    font-size: 36px;
  }
}
</style>
