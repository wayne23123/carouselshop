<script setup>
import { ref, reactive, computed } from "vue";

// 控制Carousel-------------------------------------------------------------------------------------------------------

// carouselStart 代表商品列表的 right 屬性 0px
const carouselStart = ref(-1886);

const carouselStep = 210; // 每次移動的距離

// intervalId 會被用來存放 setInterval 函數所返回的計時器ID，以便於之後停止計時器。
let intervalId = null;

// 往右移動 carouselStep 的距離，當超出最右邊時回到最左邊
function moveCarouselRight() {
  carouselStart.value += carouselStep;
  if (carouselStart.value >= 5) {
    carouselStart.value = -1886;
  }
}

// 往左移動 carouselStep 的距離，當超出最左邊時回到最左邊
function moveCarouselLeft() {
  carouselStart.value -= carouselStep;
  if (carouselStart.value < -1891) {
    carouselStart.value = 0;
  }
}

// 開始輪播，設定 intervalId 為每 2 秒執行 moveCarouselRight
function startCarousel() {
  intervalId = setInterval(moveCarouselRight, 2000);
}

startCarousel();

// 停止輪播，清除 intervalId
function stopCarousel() {
  clearInterval(intervalId);
}
</script>

<template>
  <section class="sectionCarousel">
    <div class="carouselLayout">
      <button
        @click="moveCarouselLeft"
        @mouseenter="stopCarousel"
        @mouseleave="startCarousel"
        class="carouselLeftButton"
      >
        《
      </button>
      <button
        @click="moveCarouselRight"
        @mouseenter="stopCarousel"
        @mouseleave="startCarousel"
        class="carouselRightButton"
      >
        》
      </button>
      <div
        @mouseenter="stopCarousel"
        @mouseleave="startCarousel"
        class="caroselContainer"
      >
        <ul :style="{ right: carouselStart + 'px' }" class="caroselUl dis">
          <li>
            <div class="imgLayout">
              <img src="./assets/1.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/2.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/3.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/4.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/5.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/6.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/7.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/8.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/9.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/10.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/11.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/12.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/13.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/14.png" alt="" />
            </div>
          </li>
          <li>
            <div class="imgLayout">
              <img src="./assets/15.png" alt="" />
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section>
  <section class="disCen">
    <div class="card">
      <div class="fz24">您好，歡迎來到 Wayne Lu 的商品列表練習</div>
      <div>{{ carouselStart }}</div>
      <br />
      <div>這個商品列表使用 HTML + CSS + VUE 製作而成</div>
      <div>先使用 ul li 標籤做 15 個列表並引入圖片</div>
      <div>在 html 的 ul 的 tag 標籤使用 vbind 綁定 style 的</div>
      <div>right 綁定在一個叫 carouselStart 的 ref 值</div>
      <div class="bgcVS">
        <span class="then">˂</span>
        <span class="number">ul</span> <span class="then">:</span>
        <span class="function">style</span> <span class="then">="</span>
        <span class="brackets">{</span> <span class="word">right</span>
        <span class="then">:</span> <span class="word">carouselStart</span>
        <span class="then">+</span> <span class="then">'</span>
        <span class="word">px</span> <span class="then">'</span>
        <span class="brackets">}</span> <span class="then">"</span>
        <span class="then">></span>
      </div>
      <div>目標是 做一個 function 把 carouselStart 這個 ref 值</div>
      <div>在一定時間後增加值來達到將商品列表向右方推的效果</div>
      <div class="bgcVS">
        <div>
          <span class="function">const </span>
          <span class="word">carouselStart</span>
          <span class="then">= </span> <span class="variable">ref</span>
          <span class="brackets">(</span> <span class="then">-</span>
          <span class="number">1886</span> <span class="brackets">)</span>
          <span class="then">;</span>
        </div>
        <div>
          <span class="function">function </span>
          <span class="variable">moveCarouselRight</span>
          <span class="brackets">() {</span>
        </div>
        <div class="pTwo">
          <span class="word">carouselStart</span> <span class="word">.</span>
          <span class="word">value</span> <span class="then">+=</span>
          <span class="number">210</span> <span class="then">;</span>
        </div>
        <div class="pTwo">
          <span class="then">if</span> <span class="brackets">(</span>
          <span class="word">carouselStart.value</span>
          <span class="then">>=</span> <span class="number">5</span>
          <span class="brackets">){</span>
        </div>
        <div class="pFou">
          <span class="word">carouselStart</span> <span class="word">.</span>
          <span class="word">value</span> <span class="then">=</span>
          <span class="then"> -</span><span class="number">1886</span>
          <span class="then">;</span>
        </div>
        <div class="pTwo">
          <span class="brackets">}</span>
        </div>
        <span class="brackets">}</span>
      </div>
      <div>
        一開始先定義了一個 carouselStart ref 值為 -1886
        (讓第1張剛好定位到最左邊)
      </div>
      <div>(因為載入15張寬度為210px圖片right:-1886px可以讓圖片從1開始)</div>
      <div>
        這個 moveCarouselRight 的 function 每次觸發會將 carouselStart 加上 210
      </div>
      <div>
        剛好讓圖片向左移動一張的距離 並且設定 >= 5 時(要剛好讓最後一張顯示)
      </div>
      <div>
        會重置到第一張來達到商品列表陳列的功能 並依照依樣邏輯製作了向右功能
      </div>
      <div>最後還製作 startCarousel 跟 stopCarousel function</div>
      <div>讓商品會自動輪播 以及 讓滑鼠移入商品時會停止輪播的功能</div>
      <div class="bgcVS">
        <div>
          <span class="function">let </span>
          <span class="word">intervalId</span> <span class="then">= </span>
          <span class="then">null;</span>
        </div>
        <div>
          <span class="function">function </span>
          <span class="variable">startCarousel</span>
          <span class="brackets">() {</span>
        </div>
        <div class="pTwo">
          <span class="word">intervalId</span> <span class="then">=</span>
          <span class="variable">setInterval</span>
          <span class="brackets">(</span>
          <span class="variable">moveCarouselRight,</span>
          <span class="word"></span> <span class="word"></span>
          <span class="number">2000</span> <span class="brackets">)</span>
          <span class="then">;</span>
        </div>
        <span class="brackets">}</span>
        <div>
          <span class="function">function </span>
          <span class="word">stopCarousel</span>
          <span class="brackets">() {</span>
        </div>
        <div class="pTwo">
          <span class="variable">clearInterval</span>
          <span class="brackets">(</span> <span class="word">intervalId</span>
          <span class="brackets">)</span> <span class="then">;</span>
        </div>
        <span class="brackets">}</span>
      </div>
    </div>
  </section>
</template>

<style scoped>
.fz24 {
  font-size: 24px;
}
.card {
  border: 1px black solid;
  background-color: #b4b4b4;
  padding: 20px;
}
.sectionCarousel {
  width: 100%;
  max-width: 100%;
  overflow: hidden;
}

.carouselLayout {
  width: 100%;
  height: 210px;
  background-color: rgb(112, 112, 112);
  overflow: hidden;
}

.carouselLeftButton {
  position: absolute;
  color: red;
  font-size: 30px;
  z-index: 10;
  top: 90px;
}

.carouselRightButton {
  position: absolute;
  color: red;
  font-size: 30px;
  z-index: 10;
  top: 90px;
  right: 0;
}

.caroselUl {
  list-style: none;
  transition: all 1.6s ease;
  position: absolute;
}

.imgLayout {
  width: 210px;
  height: 210px;
  background-color: #0c0c0c;
  overflow: hidden;
}

img {
  width: 100%;
  height: 100%;
}
img:hover {
  transform: scale(2);
  transition: all 1.2s ease;
}
</style>
