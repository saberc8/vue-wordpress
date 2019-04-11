<template>
  <div class="n6">
    <h1 class="n6-title">{{title}}</h1>
    <p class="n6-info">{{info}}</p>
    <div class="n6-content">
      <ul>
        <li v-for="(item,index) of content" :key="index">
          <div
            class="n6-card"
            :class="{current:currentIndex===index}"
            @mouseenter="showCard(index)"
          >
            <div v-show="currentIndex!==index">
              <div class="n6-bgimg" :style="{backgroundImage:'url('+item.imgUrl+')'}">
                <h4 class="n6-caption">{{item.title}}</h4>
                <div class="n6-mask"></div>
                <h4 class="n6-caption">{{item.title}}</h4>
              </div>
              <div>
                <p>{{item.caption}}</p>
              </div>
            </div>
            <div v-show="currentIndex===index">
              <div class="current-bg" :style="{backgroundImage:'url('+item.imgUrl+')'}">
                <div class="n6-current-mask"></div>
                <h4 class="n6-current-caption">{{item.title}}</h4>
                <p class="current-desc">{{item.desc}}</p>
              </div>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "n1",
  data() {
    return {
      currentIndex: 0,
      title: "非响应式组件N6",
      info: "非响应式组件N6,非响应式组件N6,非响应式组件N6",
      content: [
        {
          title: "内容标题1",
          imgUrl: require("../assets/images/n6-bg1.png"),
          desc:
            "基于百度天工 IOT 基础套件，垂直于智能家居方向，提供覆盖设备配网、注册、管理、控制、联动、OTA等全生命周期的一站式解决方案。帮助智能家居厂商更快捷地使用设备云服务，帮助企业节约人力成本，快速实现智能化转型"
        },
        {
          title: "内容标题2",
          imgUrl: require("../assets/images/n6-bg2.png"),
          desc:
            "天工能源物联网解决方案，是面向能源行业，融合百度智能云ABC技术和物联网技术的整体解决方案，由能源侧接入、天工物联网平台和能源应用三部分组成"
        },
        {
          title: "内容标题3",
          imgUrl: require("../assets/images/n6-bg3.png"),
          desc:
            "基于百度天工 IOT 基础套件，垂直于智能家居方向，提供覆盖设备配网、注册、管理、控制、联动、OTA等全生命周期的一站式解决方案。帮助智能家居厂商更快捷地使用设备云服务，帮助企业节约人力成本，快速实现智能化转型"
        },
        {
          title: "内容标题4",
          imgUrl: require("../assets/images/n6-bg4.png"),
          desc:
            "天工能源物联网解决方案，是面向能源行业，融合百度智能云ABC技术和物联网技术的整体解决方案，由能源侧接入、天工物联网平台和能源应用三部分组成"
        },
        {
          title: "内容标题5",
          imgUrl: require("../assets/images/n6-bg5.png"),
          desc:
            "天工能源物联网解决方案，是面向能源行业，融合百度智能云ABC技术和物联网技术的整体解决方案，由能源侧接入、天工物联网平台和能源应用三部分组成"
        }
      ]
    };
  },
  methods: {
    showCard(index) {
      this.currentIndex = index;
    }
  }
};
</script>

<style scoped>
.n6 {
  text-align: center;
  background-size: cover;
  position: relative;
  background: linear-gradient(-1deg, #3c4255 0, #2a2f40 98%);
  height: 660px;
  color: #fff;
}
h1 {
  position: relative;
  display: inline-block;
  margin: 50px auto 20px;
  line-height: 30px;
  padding: 0 30px;
  font-weight: 400;
  font-size: 28px;
  color: #fff;
}
.n6-info {
  color: #fff;
}
h1::before {
  content: "";
  width: 66px;
  height: 13px;
  background: url(../assets/images/n1_r.png) no-repeat center;
  background-size: contain;
  position: absolute;
  top: 5px;
  left: 100%;
}
h1::after {
  content: "";
  width: 66px;
  height: 13px;
  background: url(../assets/images/n1_l.png) no-repeat center;
  background-size: contain;
  position: absolute;
  top: 5px;
  right: 100%;
}
.n6-content ul {
  display: flex;
  justify-content: center;
  padding: 0;
  margin-top: 60px;
  margin-bottom: 0;
}
.n6-content::after {
  content: "";
  clear: both;
  display: block;
}
.n6-card {
  position: relative;
  width: 200px;
  height: 390px;
  text-align: center;
  transition: opacity, height, margin 0.3s linear;
  overflow: hidden;
}
.n6-caption {
  position: absolute;
  color: #fff;
  z-index: 99;
  left: 0;
  right: 0;
  margin: auto;
  top: 40%;
}
.n6-current-caption {
  position: absolute;
  color: #fff;
  z-index: 99;
  left: 0;
  right: 0;
  margin: auto;
  top: 20%;
}
.current {
  position: relative;
  width: 280px;
  height: 380px;
  padding: 30px;
  margin-top: -25px;
  background-repeat: repeat;
  overflow: hidden;
}
.current-bg {
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  opacity: 0.77;
  background: center;
  background-size: 100% 100%;
}
.n6-bgimg {
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  opacity: 0.77;
  background: center;
  background-size: 100% 100%;
}
.n6-caption::after {
  content: " ";
  display: block;
  width: 30px;
  height: 4px;
  background: #40acff;
  margin: 16px auto 0 auto;
}
.n6-current-caption::after {
  content: " ";
  display: block;
  width: 30px;
  height: 4px;
  background: #40acff;
  margin: 16px auto 0 auto;
}
.n6-caption-l::after {
  content: " ";
  display: block;
  width: 30px;
  height: 2px;
  background: #108ced;
  margin: 16px auto 0 auto;
}
.n6-icon-l {
  width: 30px;
}
.n6-mask {
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  opacity: 0.77;
  background-image: linear-gradient(-180deg, #364167 0, #0a0b13 100%);
}
.current-desc {
  position: absolute;
  margin: 0;
  padding: 200px 30px;
  font-size: 14px;
  line-height: 24px;
  font-size: 12px;
}
.n6-current-mask {
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  opacity: 0.82;
  background-image: linear-gradient(-180deg, #3f6493 0, #1c192b 100%);
}
</style>