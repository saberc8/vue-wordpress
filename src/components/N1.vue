<template>
  <div class="n1">
    <h1 class="n1-title">{{title}}</h1>
    <p class="n1-info">{{info}}</p>
    <div class="n1-content">
      <ul>
        <li v-for="(item,index) of content" :key="index">
          <div
            class="n1-bg"
            :style="{backgroundImage:'url('+item.imgUrl+')'}"
            :class="{ 'n1-bg-enter':  currentEnter===index ,'n1-bg-leave': currentLeave===index}"
            @mouseenter="imgMoveStart(index)"
            @mouseout="imgMoveEnd(index)"
          ></div>
          <p class="n1-bg-caption">{{item.caption}}</p>
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
      currentEnter: null,
      currentLeave: null,
      title: "非响应式组件N1",
      info: "非响应式组件N1,非响应式组件N1,非响应式组件N1",
      content: [
        {
          imgUrl: require("../assets/images/n1-1.png"),
          caption: "大数据"
        },
        {
          imgUrl: require("../assets/images/n1-2.png"),
          caption: "云计算"
        },
        {
          imgUrl: require("../assets/images/n1-3.png"),
          caption: "人工智能"
        },
        {
          imgUrl: require("../assets/images/n1-4.png"),
          caption: "数据加工"
        },
        {
          imgUrl: require("../assets/images/n1-5.png"),
          caption: "人工智能"
        },
        {
          imgUrl: require("../assets/images/n1-6.png"),
          caption: "云计算"
        },
        {
          imgUrl: require("../assets/images/n1-7.png"),
          caption: "人工智能"
        },
        {
          imgUrl: require("../assets/images/n1-8.png"),
          caption: "云计算"
        },
        {
          imgUrl: require("../assets/images/n1-9.png"),
          caption: "人工智能"
        },
        {
          imgUrl: require("../assets/images/n1-10.png"),
          caption: "数据加工"
        },
        {
          imgUrl: require("../assets/images/n1-11.png"),
          caption: "人工智能"
        },
        {
          imgUrl: require("../assets/images/n1-12.png"),
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
.n1 {
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
.n1-bg {
  width: 140px;
  height: 140px;
  display: block;
  margin: auto;
  background-size: cover;
  background-position: 0 140px;
}
.n1-bg-enter {
  animation: enter 400ms steps(25) both;
}
.n1-bg-leave {
  animation: leave 400ms steps(25) both;
}
/* .n1-content {
  overflow:hidden;
} */
.n1-content::after {
  content: "";
  clear: both;
  display: block;
}
.n1-content ul {
  margin: 0 auto;
  width: 840px;
}
.n1-content ul li {
  float: left;
}
.n1-content ul li::after {
  content: "";
  clear: both;
}
.n1-content ul li:hover {
  font-weight: 700;
}
.n1-bg-caption {
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
@keyframes leave {
  0% {
    background-position: 0 3640px;
  }
  90% {
    background-position: 0 140px;
  }
  100% {
    background-position: 0 140px;
  }
}
</style>


