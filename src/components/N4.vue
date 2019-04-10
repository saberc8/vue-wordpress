<template>
  <div class="n4">
    <h1 class="n4-title">{{title}}</h1>
    <p class="n4-info">{{info}}</p>
    <swiper class="swiper" :options="swiperOption" ref="mySwiper" @someSwiperEvent="callback">
      <!-- slides -->
      <swiper-slide class="swiper-item" v-for="(item,index) of content" :key="index">
        <div>
          <p class="n4-date">2019</p>
          <p class="n4-caption">{{item.caption}}</p>
          <div class="n4-view">
            <a class="n4-icon" href>VIEW</a>
          </div>
          <p class="n4-desc">{{item.desc}}</p>
          <div class="n4-img">
            <img :src="item.imgUrl" alt>
          </div>
        </div>
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
      <div class="swiper-scrollbar" slot="scrollbar"></div>
    </swiper>
  </div>
</template>

<script>
import "swiper/dist/css/swiper.css";
import { swiper, swiperSlide } from "vue-awesome-swiper";
export default {
  name: "n4",
  components: {
    swiper,
    swiperSlide
  },
  data() {
    return {
      swiperOption: {
        slidesPerView: "auto",
        scrollbar: {
          el: ".swiper-scrollbar"
        },
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev"
        }
      },
      currentEnter: null,
      currentLeave: null,
      title: "非响应式组件n4",
      info: "非响应式组件n4,非响应式组件n4,非响应式组件n4",
      content: [
        {
          imgUrl: require("../assets/images/n4-1.jpg"),
          caption:
            "力压海外巨头突破人机对话难题，阿里获DSTC7国际大赛双料冠军！",
          desc:
            "信息革命、移动互联网革命尚未落幕，智能革命又像一头大象一样撞进人类的生活，激荡着整个世界。任何足够先进的科技，初看都与魔法无异，但魔法背后是对规律和趋势的洞悉。今天，达摩院发布2019十大科技趋势。我们希望，在魔法抵达之前，让科技演进的脉搏清晰可见。"
        },
        {
          imgUrl: require("../assets/images/n4-2.jpg"),
          caption: "力压海外巨头突破人机对话难题",
          desc:
            "自主研发、拿下两个世界第一，阿里人机对话模型成通用标准！读懂人类潜藏的真实意图，阿里AI再获两个世界冠军！"
        },
        {
          imgUrl: require("../assets/images/n4-2.jpg"),
          caption: "力压海外巨头突破人机对话难题",
          desc:
            "自主研发、拿下两个世界第一，阿里人机对话模型成通用标准！读懂人类潜藏的真实意图，阿里AI再获两个世界冠军！"
        },
        {
          imgUrl: require("../assets/images/n4-2.jpg"),
          caption: "力压海外巨头突破人机对话难题",
          desc:
            "自主研发、拿下两个世界第一，阿里人机对话模型成通用标准！读懂人类潜藏的真实意图，阿里AI再获两个世界冠军！"
        },
        {
          imgUrl: require("../assets/images/n4-2.jpg"),
          caption: "力压海外巨头突破人机对话难题",
          desc:
            "自主研发、拿下两个世界第一，阿里人机对话模型成通用标准！读懂人类潜藏的真实意图，阿里AI再获两个世界冠军！"
        },
        {
          imgUrl: require("../assets/images/n4-2.jpg"),
          caption: "力压海外巨头突破人机对话难题",
          desc:
            "自主研发、拿下两个世界第一，阿里人机对话模型成通用标准！读懂人类潜藏的真实意图，阿里AI再获两个世界冠军！"
        },
        {
          imgUrl: require("../assets/images/n4-2.jpg"),
          caption: "力压海外巨头突破人机对话难题",
          desc:
            "自主研发、拿下两个世界第一，阿里人机对话模型成通用标准！读懂人类潜藏的真实意图，阿里AI再获两个世界冠军！"
        }
      ]
    };
  },
  methods: {
    imgMoveStart(index) {
      this.currentEnter = index;
      this.currentLeave = null;
    },
    imgMoveEnd(index) {
      this.currentLeave = index;
      this.currentEnter = null;
    }
  }
};
</script>

<style scoped>
.n4 {
  text-align: center;
  margin-top: 100px;
  height: 700px;
  overflow: hidden;
}
h1 {
  position: relative;
  display: inline-block;
  margin: 0 auto 20px;
  line-height: 30px;
  padding: 0 30px;
  font-weight: 400;
  font-size: 28px;
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
.swiper {
  margin: 30px;
}
.n4-content::after {
  content: "";
  clear: both;
  display: block;
}
.swiper-item {
  width: 360px;
  height: 500px;
  padding: 20px;
  text-align: center;
  font-size: 16px;
  background: #fff;
  box-shadow: 0 0 10px 0 rgba(27, 43, 79, 0.2);
  margin: 0 12px 4px;
  overflow: hidden;
}
.swiper-item:hover {
  box-shadow: 0 0 10px 0 rgba(27, 43, 79, 0.4);
}
.n4-date {
  opacity: 0.8;
  font-family: Roboto;
  font-weight: 800;
  font-size: 12px;
  color: #1b2b4f;
  letter-spacing: 2px;
  text-align: center;
  line-height: 16px;
  margin: 0;
}
.n4-caption {
  font-size: 24px;
  color: #1b2b4f;
  text-align: center;
  line-height: 40px;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  height: 80px;
  -webkit-box-orient: vertical;
}
.n4-desc {
  padding-right: 20px;
  opacity: 0.6;
  font-size: 14px;
  color: #1b2b4f;
  text-align: left;
  line-height: 28px;
  position: absolute;
  bottom: 240px;
  font-family: PingFangSC;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  height: 84px;
  -webkit-box-orient: vertical;
}
.n4-icon {
  background: url(../assets/images/n4-icon.png) right center no-repeat;
  padding-right: 5px;
  font-size: 12px;
  line-height: 12px;
  color: #d00000;
  letter-spacing: 3px;
  text-align: center;
  font-family: Roboto;
  font-weight: 700;
  text-decoration: none;
}
.n4-view {
  position: absolute;
  text-align: center;
  top: 160px;
  left: 0;
  right: 0;
  margin: 0 auto;
}
.n4-img {
  width: 360px;
  height: 210px;
  position: absolute;
  bottom: 20px;
  overflow: hidden;
}
.n4-img img {
  width: 360px;
  height: 210px;
  transition-duration: 0.5s;
}
.n4-img img:hover {
  transform: scale(1.1);
}
</style>


