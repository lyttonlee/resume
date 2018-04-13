<template>
  <div
  class="resume"
  @mousewheel="mouse"
  :style="{
    backgroundImage:`url(${img})`,
    height: `${clientHeight}`
  }">
    <transition
      :duration="{ enter: 2500, leave: 1500 }"
      :leave-active-class="'animated ' + leaveanimate"
      :enter-active-class="'animated ' + enteranimate">
      <div class="section" :style="{height: `${clientHeight}`}" v-if="init === 1">
        <div class="sec">
          <Con1></Con1>
        </div>
      </div>
    </transition>
    <transition
      :duration="{ enter: 2500, leave: 1500 }"
      :leave-active-class="'animated ' + leaveanimate"
      :enter-active-class="'animated ' + enteranimate">
      <div class="section" :style="{height: `${clientHeight}`}" v-if="init === 2">
        <div class="sec">
          <Con2></Con2>
        </div>
      </div>
    </transition>
    <transition
      :duration="{ enter: 1500, leave: 1500 }"
      :leave-active-class="'animated ' + leaveanimate"
      :enter-active-class="'animated ' + enteranimate">
      <div class="section" :style="{height: `${clientHeight}`}" v-if="init === 3">
        <div class="sec">
          <Con3></Con3>
        </div>
      </div>
    </transition>
    <transition
      :duration="{ enter: 1500, leave: 1500 }"
      :leave-active-class="'animated ' + leaveanimate"
      :enter-active-class="'animated ' + enteranimate">
      <div class="section" :style="{height: `${clientHeight}`}" v-if="init === 4">
        <div class="sec">
          <Con4></Con4>
        </div>
      </div>
    </transition>
    <!-- 下方的下一页按钮 -->
    <div class="next"><i class="iconfont icon-xiala setarrow" @click="nextPage"></i></div>
  </div>
</template>
<script>
import Con1 from '@/components/compon1'
import Con2 from '@/components/compon2'
import Con3 from '@/components/compon3'
import Con4 from '@/components/compon4'
export default {
  components: {
    Con1,
    Con2,
    Con3,
    Con4
  },
  data () {
    return {
      // ..
      img: require('../../static/img/bg2.jpg'),
      clientHeight: '900px',
      init: 1,
      lastscroll: 0,
      leaveanimate: 'zoomOutUp',
      enteranimate: 'zoomInDown'
    }
  },
  methods: {
    mouse (event) {
      // 防止用户短时间内滚动多次，设置滚动间隔大于一秒才能生效
      // 判断滚动间隔时间
      let scrollduration = event.timeStamp - this.lastscroll
      console.log(scrollduration)
      if (scrollduration > 1000) {
        // 将这一次的滚动时间记录为上一次合法的滚动时间
        this.lastscroll = event.timeStamp
        console.log('合法的滚动')
        // 判断滚动方向进行操作
        if (event.deltaY > 0) {
          console.log('down')
          if (this.init === 4) {
            this.init = 1
          } else {
            this.init = this.init + 1
          }
        } else {
          console.log('up')
          if (this.init === 1) {
            this.init = 4
          } else {
            this.init = this.init - 1
          }
        }
      } else {
        // 如果滚动不合法就不做任何操作
        console.log('请爱护你的鼠标不要连续滚动！')
      }
    },
    nextPage () {
      if (this.init === 4) {
        this.init = 1
      } else {
        this.init = this.init + 1
      }
    }
  },
  mounted () {
    this.clientHeight = `${document.documentElement.clientHeight}px`
    // 然后监听window的resize事件．在浏览器窗口变化时再设置下背景图高度
    window.onresize = () => {
      this.clientHeight = `${document.documentElement.clientHeight}px`
      console.log(this.clientHeight)
    }
  }
}
</script>
<style lang="less" scoped>
@import '../less/index.less';
.position {
  position: fixed;
  top: 0;
  left: 0;
}
.position-right {
  position: fixed;
  top: 50%;
  right: 20px;
}
.position-bottom {
  position: fixed;
  bottom: 20px;
  left: 47%;
}
@-moz-keyframes myfirst {
  0%, 20%, 50%, 80%, 100% {
    -moz-transform: translateY(0);
    transform: translateY(0);
  }
  40% {
    -moz-transform: translateY(-30px);
    transform: translateY(-30px);
  }
  60% {
    -moz-transform: translateY(-15px);
    transform: translateY(-15px);
  }
}
@-webkit-keyframes myfirst {
  0%, 20%, 50%, 80%, 100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }
  40% {
    -webkit-transform: translateY(-30px);
    transform: translateY(-30px);
  }
  60% {
    -webkit-transform: translateY(-15px);
    transform: translateY(-15px);
  }
}
@keyframes myfirst {
  0%, 20%, 50%, 80%, 100% {
    -moz-transform: translateY(0);
    -ms-transform: translateY(0);
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }
  40% {
    -moz-transform: translateY(-30px);
    -ms-transform: translateY(-30px);
    -webkit-transform: translateY(-30px);
    transform: translateY(-30px);
  }
  60% {
    -moz-transform: translateY(-15px);
    -ms-transform: translateY(-15px);
    -webkit-transform: translateY(-15px);
    transform: translateY(-15px);
  }
}
.resume {
  width: 100%;
  height: 100%;
  background-repeat:no-repeat;
  background-position: center center;
  background-size:100% 100%;
  -moz-background-size:100% 100%;
  // opacity: .7;
  .section {
    width: 100%;
    background: rgba(255, 255, 255, .3);
    .position;
    .sec {
      width: 100%;
    }
  }
  .next {
    // .position-bottom;
    .setarrow {
      // position:relative;
      .position-bottom;
      font-size: 40px;
      color: rgba(4, 10, 41, 0.8);
      opacity: .8;
      cursor: pointer;
      animation: myfirst 5s infinite;
      @media screen and (max-width: 768px) {
        font-size: 20px;
      }
    }
  }
}
</style>
