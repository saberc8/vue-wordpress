<template>
  <div class="n1">
    <h1 class="n1-title">全链路服务</h1>
    <p class="n1-info">30年技术沉淀，50+产品服务，助力企业智能转型</p>
    <div class="n1-content">
      <ul>
        <li>
          <div
            class="n1-bg"
            :style="{backgroundImage:'url('+require('../assets/images/n1-1.png')+')'}"
          ></div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "n1"
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
}
</style>


