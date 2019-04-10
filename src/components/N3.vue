<template>
  <div class="n3">
    <h1 class="n3-title">{{title}}</h1>
    <p class="n3-info">{{info}}</p>
    <div class="n3-content">
      <ul>
        <li v-for="(item,index) of content" :key="index">
          <div class="n3-bg" :style="{backgroundImage:'url('+item.imgUrl+')'}">
            <div class="n3-masking">
              <p class="n3-caption">{{item.caption}}</p>
              <p class="n3-desc">{{item.desc}}</p>
            </div>
          </div>
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
          caption: "大数据",
          desc:
            "今目标通过主线、文档、合作伙伴等应用，实现了建筑企业流程标准可控、项目远程管理、多方有效协同的需求，确保优秀项目经验的积累和传承。"
        },
        {
          imgUrl: require("../assets/images/n3-2.png"),
          caption: "云计算",
          desc:
            "今目标通过主线、文档、合作伙伴等应用，实现了建筑企业流程标准可控、项目远程管理、多方有效协同的需求，确保优秀项目经验的积累和传承。"
        },
        {
          imgUrl: require("../assets/images/n3-3.png"),
          caption: "人工智能",
          desc:
            "今目标通过主线、文档、合作伙伴等应用，实现了建筑企业流程标准可控、项目远程管理、多方有效协同的需求，确保优秀项目经验的积累和传承。"
        },
        {
          imgUrl: require("../assets/images/n3-4.png"),
          caption: "数据加工",
          desc:
            "今目标通过主线、文档、合作伙伴等应用，实现了建筑企业流程标准可控、项目远程管理、多方有效协同的需求，确保优秀项目经验的积累和传承。"
        },
        {
          imgUrl: require("../assets/images/n3-5.png"),
          caption: "人工智能",
          desc:
            "今目标通过主线、文档、合作伙伴等应用，实现了建筑企业流程标准可控、项目远程管理、多方有效协同的需求，确保优秀项目经验的积累和传承。"
        },
        {
          imgUrl: require("../assets/images/n3-6.png"),
          caption: "云计算",
          desc:
            "今目标通过主线、文档、合作伙伴等应用，实现了建筑企业流程标准可控、项目远程管理、多方有效协同的需求，确保优秀项目经验的积累和传承。"
        },
        {
          imgUrl: require("../assets/images/n3-7.png"),
          caption: "人工智能",
          desc:
            "今目标通过主线、文档、合作伙伴等应用，实现了建筑企业流程标准可控、项目远程管理、多方有效协同的需求，确保优秀项目经验的积累和传承。"
        },
        {
          imgUrl: require("../assets/images/n3-8.png"),
          caption: "云计算",
          desc:
            "今目标通过主线、文档、合作伙伴等应用，实现了建筑企业流程标准可控、项目远程管理、多方有效协同的需求，确保优秀项目经验的积累和传承。"
        }
      ]
    };
  },
  methods: {}
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
  position: relative;
  width: 286px;
  height: 200px;
  display: block;
  margin: auto;
  background-size: cover;
  background-position: 0 0;
  overflow: hidden;
}
.n3-masking {
  position: absolute;
  width: 286px;
  height: 200px;
  transform: translateY(150px);
  background-color: rgba(0, 0, 0, 0.7);
  transition: 0.3s ease-in;
}
.n3-bg :hover {
  transform: translateY(0px);
  transition: 0.3s ease-in;
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
.n3-caption {
  position: relative;
  display: inline-block;
  font-size: 18px;
  color: #ffffff;
  line-height: 25px;
  margin-top: 15px;
  margin-bottom: 10px;
}
.n3-desc {
  position: relative;
  display: inline-block;
  font-size: 14px;
  color: #ffffff;
  line-height: 25px;
  margin: 10px 20px;
}
</style>


