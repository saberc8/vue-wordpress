<template>
  <div class="n3">
    <h1 class="n3-title">{{title}}</h1>
    <p class="n3-info">{{info}}</p>
    <div class="n3-content">
      <ul>
        <li v-for="(item,index) of content" :key="index">
          <div class="n3-bg" :style="{backgroundImage:'url('+item.imgUrl+')'}"></div>
          <p class="n3-bg-caption">{{item.caption}}</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "n3",
  data() {
    return {
      currentEnter: null,
      currentLeave: null,
      title: "非响应式组件n3",
      info: "非响应式组件n3,非响应式组件n3,非响应式组件n3",
      content: [
        {
          imgUrl: require("../assets/images/n3-1.png"),
          caption: "大数据"
        },
        {
          imgUrl: require("../assets/images/n3-2.png"),
          caption: "云计算"
        },
        {
          imgUrl: require("../assets/images/n3-3.png"),
          caption: "人工智能"
        },
        {
          imgUrl: require("../assets/images/n3-4.png"),
          caption: "数据加工"
        },
        {
          imgUrl: require("../assets/images/n3-5.png"),
          caption: "人工智能"
        },
        {
          imgUrl: require("../assets/images/n3-6.png"),
          caption: "云计算"
        },
        {
          imgUrl: require("../assets/images/n3-7.png"),
          caption: "人工智能"
        },
        {
          imgUrl: require("../assets/images/n3-8.png"),
          caption: "云计算"
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
.n3 {
  text-align: center;
  margin-top: 100px;
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
.n3-bg {
  width: 286px;
  height: 200px;
  display: block;
  margin: auto;
  background-size: cover;
  background-position: 0 0;
}
.n3-content::after {
  content: "";
  clear: both;
  display: block;
}
.n3-content ul {
  margin: 20px auto;
  width: 1280px;
}
.n3-content ul li {
  float: left;
  width: 286px;
  margin: 0 6px 12px;
}
.n3-content ul li:hover {
  font-weight: 700;
}
.n3-bg-caption {
  position: relative;
  display: inline-block;
  font-size: 18px;
  color: #383e63;
  line-height: 25px;
  margin-top: 10px;
  margin-bottom: 40px;
}
@keyframes enter {
  0% {
    background-position: 0 140px;
  }
  90% {
    background-position: 0 3640px;
  }
  100% {
    background-position: 0 3640px;
  }
}
</style>


