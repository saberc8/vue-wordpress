<template>
  <div class="n2">
    <h1 class="n2-title">{{title}}</h1>
    <p class="n2-info">{{info}}</p>
    <div class="n2-content">
      <ul>
        <li v-for="(item,index) of content" :key="index">
          <div
            class="n2-card"
            :class="{current:currentIndex===index}"
            @mouseenter="showCard(index)"
          >
            <div v-show="currentIndex!==index">
              <img class="n2-icon" :src="item.imgUrl" alt>
              <h4 class="n2-caption">{{item.title}}</h4>
              <span></span>
            </div>
            <div v-show="currentIndex===index">
              <img class="n2-icon-l" :src="item.imgUrl" alt>
              <h4 class="n2-caption-l">{{item.title}}</h4>
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
      title: "非响应式组件N2",
      info: "非响应式组件N2,非响应式组件N2,非响应式组件N2",
      content: [
        {
          title: "内容标题1",
          imgUrl: require("../assets/images/n2-1.png"),
          cpation:[]
        },
        {
          title: "内容标题2",
          imgUrl: require("../assets/images/n2-2.png")
        },
        {
          title: "内容标题3",
          imgUrl: require("../assets/images/n2-3.png")
        },
        {
          title: "内容标题4",
          imgUrl: require("../assets/images/n2-4.png")
        },
        {
          title: "内容标题5",
          imgUrl: require("../assets/images/n2-5.png")
        },
        {
          title: "内容标题6",
          imgUrl: require("../assets/images/n2-6.png")
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
.n2 {
  text-align: center;
  background-size: cover;
  background: #000 url(../assets/images/n2-bg.png) no-repeat center;
  transition: background-position 0.5s ease-out;
  height: 680px;
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
.n2-info {
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
.n2-content ul {
  display: flex;
  justify-content: center;
  padding: 0;
  margin-top: 60px;
  margin-bottom: 0;
}
.n2-content::after {
  content: "";
  clear: both;
  display: block;
}
.n2-card {
  width: 136px;
  height: 390px;
  margin-right: 1px;
  color: #fff;
  text-align: center;
  background-image: linear-gradient(
    to top,
    rgba(47, 42, 65, 0.50196) 0%,
    #2e3d50 100%
  );
  background-repeat: repeat;
  transition: opacity, height, margin 0.3s linear;
}
.current {
  width: 160px;
  height: 380px;
  padding: 30px;
  margin-top: -25px;
  background-image: linear-gradient(to top, #51436c 0%, #3a7aca 100%);
  background-repeat: repeat;
  text-align: left;
}
.n2-icon {
  width: 40px;
  margin: 30px auto 0;
}
.n2-caption::after {
  content: " ";
  display: block;
  width: 30px;
  height: 2px;
  background: #fff;
  margin: 16px auto 0 auto;
}
.n2-icon-l{
  width: 30px;
}
</style>