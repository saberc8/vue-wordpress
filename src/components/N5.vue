<template>
  <div class="n5">
    <h1 class="n5-title">{{title}}</h1>
    <p class="n5-info">{{info}}</p>
    <div class="n5-content">
      <ul>
        <li v-for="(item,index) of content" :key="index">
          <p class="n5-date">{{item.date}}</p>
          <p class="n5-caption">{{item.caption}}</p>
          <i :style="{backgroundImage:'url('+item.imgUrl+')'}"></i>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "n5",
  data() {
    return {
      currentEnter: null,
      currentLeave: null,
      title: "非响应式组件n5",
      info: "非响应式组件n5,非响应式组件n5,非响应式组件n5",
      content: [
        {
          imgUrl: require("../assets/images/n5-1.png"),
          caption: "历程一",
          date: "2017-05-26"
        },
        {
          imgUrl: require("../assets/images/n5-2.png"),
          caption: "历程二",
          date: "2018-01-22"
        },
        {
          imgUrl: require("../assets/images/n5-3.png"),
          caption: "历程三",
          date: "2018-05-16"
        },
        {
          imgUrl: require("../assets/images/n5-4.png"),
          caption: "历程四",
          date: "2018-12-22"
        },
        {
          imgUrl: require("../assets/images/n5-5.png"),
          caption: "历程五",
          date: "2019-01-06"
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
.n5 {
  text-align: center;
  margin-top: 100px;
  background: url(../assets/images/n5-bg.jpg) no-repeat center;
  margin-bottom: 100px;
  background-size: cover;
  height: 500px;
}
h1 {
  position: relative;
  display: inline-block;
  margin: 0 auto 20px;
  line-height: 30px;
  padding: 0 30px;
  font-weight: 400;
  font-size: 28px;
  color: #fff;
  margin-top: 100px;
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
.n5-info {
  color: #fff;
}
.n5-content {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
}
.n5-content::after {
  content: "";
  clear: both;
  display: block;
}
.n5-content ul {
  margin-top: 80px;
  display: flex;
  min-width: 1200px;
  position: relative;
}
.n5-content ul::after {
  content: "";
  width: 25%;
  height: 12px;
  background: url(../assets/images/n5-6.png) no-repeat;
  background-position: right center;
  position: absolute;
  top: 60px;
  left: 75%;
  z-index: 0;
  box-sizing: inherit;
}
.n5-content ul li {
  width: 20%;
  position: relative;
  transition: all 0.3s;
}
li::after {
  content: "";
  width: 2px;
  height: 90px;
  background: url(../assets/images/n5-line.png) no-repeat;
  background-size: 100% 100%;
  position: absolute;
  right: calc(50% + 5px);
  top: 20px;
  transform: scale(0);
  transition: all 0.3s;
  z-index: 1;
}
li:hover::after {
  transform: scale(1);
}
.n5-date {
  font-size: 16px;
  line-height: 28px;
  margin-bottom: 50px;
  color: #bfcaff;
  opacity: 0.9;
  transition: all 0.3s;
}
.n5-caption {
  color: #bfcaff;
  opacity: 0.9;
  transition: all 0.3s;
}
.n5-bg-caption {
  position: relative;
  display: inline-block;
  font-size: 18px;
  color: #383e63;
  line-height: 25px;
  margin-top: 10px;
  margin-bottom: 40px;
}
i {
  position: absolute;
  width: 100%;
  height: 12px;
  background: no-repeat;
  background-size: contain;
  background-position: right center;
  left: -50%;
  top: 60px;
  z-index: 1;
}
.n5-scale {
  height: 60px;
}
li:hover {
  transform: scale(1.1);
}
li:hover .n5-date {
  color: #fff;
  transform: scale(1.1) translatey(-20px);
}
li:hover .n5-caption {
  color: #fff;
  transform: scale(1.1) translatey(20px);
}
li:hover i {
  transform: scale(1);
}
</style>


