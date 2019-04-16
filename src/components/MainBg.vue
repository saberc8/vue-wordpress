<template>
<div class="mainbg">
  <div class="card">
      <div class="card-back">
          <div class="line-numbers">
              <div>1</div>
              <div>2</div>
              <div>3</div>
              <div>4</div>
              <div>5</div>
              <div>6</div>
              <div>7</div>
              <div>8</div>
              <div>9</div>
          </div>
          <code>
            <span class="variable">const </span><span class="function">aboutMe </span><span class="operator">= </span><span>{</span>
            <div class="indent"> 
              <span class="property">name</span><span class="operator">: </span><span class="string">'Yu Senlin'</span><span>,</span>
            </div>
            <div class="indent">
              <span class="property">work</span><span class="operator">: </span><span class="string">'Front-end Engineer'</span><span>,</span>
            </div>
            <div class="indent">
              <span class="property">contact</span><span class="operator">: </span><span>{</span>
              <div class="indent">
                <span class="property">email</span><span class="operator">: </span><span class="string">'yusenlin1122@qq.com'</span><span>,</span>
              </div>
              <div class="indent">
                <span class="property">website</span><span class="operator">:</span><span class="string">'https://blog.saberc8.cn'</span><span>,</span>
              </div>
              <div class="indent">
                <span class="property">wechat</span><span class="operator">:</span><span class="string">'mumu2sama'</span>
              </div>
              <span>}</span>
            </div>
            <span>}</span>
          </code>
        </div>
      <div class="card-front">
          <div class="line-numbers">
              <div>1</div>
              <div>2</div>
              <div>3</div>
              <div>4</div>
              <div>5</div>
              <div>6</div>
              <div>7</div>
              <div>8</div>
              <div>9</div>
          </div>
          <code>
            <span class="variable">this</span><span>.</span><span class="method">addEventListener</span><span>(</span><span class="string">'mouseover'</span><span>, </span><span class="function">() => </span><span>{ </span>
            <div class="indent">
              <span class="variable">this</span><span>.</span><span class="property">flipCard </span><span>= </span><span class="boolean">true</span><span>;</span>
            </div>
            <span>});</span>
          </code>
        </div>
  </div>
</div>
 
</template>

<style scoped>
*,
*:before,
*:after {
  box-sizing: border-box;
  outline: none;
}

.mainbg {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 90vh;
  background: linear-gradient(45deg, #446af1, #e478f7);
   font-family: "Source Sans Pro", sans-serif;
  font-size: 16px;
  font-weight: 300;
  line-height: 1.5;
  color: #444;
}

code,
.card .line-numbers {
  font-family: "Lucida Console", Monaco, monospace;
  font-size: 14px;
}
.card {
  position: relative;
  width: 30rem;
  height: 15rem;
  perspective: 150rem;
}
.card-front,
.card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: auto;
  border-radius: 5px;
  box-shadow: 0 1.5rem 4rem rgba(0, 0, 0, 0.4);
  transition: 0.9s cubic-bezier(0.25, 0.8, 0.25, 1);
  backface-visibility: hidden;
  overflow: hidden;
}
.card-front:before,
.card-front:after,
.card-back:before,
.card-back:after {
  position: absolute;
}
.card-front:before,
.card-back:before {
  top: -40px;
  right: -40px;
  content: "";
  width: 80px;
  height: 80px;
  background-color: rgba(255, 255, 255, 0.08);
  transform: rotate(45deg);
  z-index: 1;
}
.card-front:after,
.card-back:after {
  content: "+";
  top: 0;
  right: 5px;
  font-size: 24px;
  transform: rotate(45deg);
  z-index: 2;
}
.card-front {
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, #101010, #2c3e50);
}
.card-front:after {
  color: #212f3c;
}
.card-back {
  background: linear-gradient(-45deg, #101010, #2c3e50);
  transform: rotateX(180deg);
}
.card-back:after {
  color: #11181f;
}
.card:hover .card-front {
  transform: rotateX(-180deg);
}
.card:hover .card-back {
  transform: rotateX(0deg);
}
.card .line-numbers {
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
  margin: 0;
  padding: 0 10px;
  background-color: rgba(255, 255, 255, 0.03);
  font-size: 13px;
}
.card .line-numbers > div {
  padding: 2.5px 0;
  opacity: 0.15;
}
.card code,
.card .line-numbers {
  color: whitesmoke;
}
.card .indent {
  padding-left: 30px;
}
.card .operator {
  color: #4dd0e1;
}
.card .string {
  color: #9ccc65;
}
.card .variable {
  color: #ba68c8;
}
.card .property {
  color: #ef5350;
}
.card .method {
  color: #29b6f6;
}
.card .function {
  color: #fdd835;
}
.card .boolean {
  color: #4dd0e1;
}
</style>
