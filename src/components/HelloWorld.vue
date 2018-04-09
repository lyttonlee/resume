<template>
  <div
  class="resume"
  @mousewheel="mouse"
  :style="{
    backgroundImage:`url(${img})`,
    height: `${clientHeight}`
  }">
    <transition
      :duration="{ enter: 1500, leave: 1500 }"
      leave-active-class="animated zoomOutRight"
      enter-active-class="animated zoomInLeft">
      <div class="section" :style="{height: `${clientHeight}`}" v-if="init === 1">
        <div class="sec">
          <Con1></Con1>
        </div>
      </div>
    </transition>
    <transition
      :duration="{ enter: 1500, leave: 1500 }"
      leave-active-class="animated zoomOutRight"
      enter-active-class="animated zoomInLeft">
      <div class="section" :style="{height: `${clientHeight}`}" v-if="init === 2">
        <div class="sec">
          <Con2></Con2>
        </div>
      </div>
    </transition>
    <transition
      :duration="{ enter: 1500, leave: 1500 }"
      leave-active-class="animated zoomOutRight"
      enter-active-class="animated zoomInLeft">
      <div class="section" :style="{height: `${clientHeight}`}" v-if="init === 3">
        <div class="sec">
          <Con3></Con3>
        </div>
      </div>
    </transition>
    <transition
      :duration="{ enter: 1500, leave: 1500 }"
      leave-active-class="animated zoomOutRight"
      enter-active-class="animated zoomInLeft">
      <div class="section" :style="{height: `${clientHeight}`}" v-if="init === 4">
        <div class="sec">
          <Con4></Con4>
        </div>
      </div>
    </transition>
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
      img: require('../../static/img/bg.jpg'),
      clientHeight: '900px',
      init: 1
    }
  },
  methods: {
    mouse (event) {
      // console.log(event)
      // console.log(document.documentElement.clientHeight)
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
          this.init = 1
        } else {
          this.init = this.init - 1
        }
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
.position {
  position: fixed;
  top: 0;
  left: 0;
}
.resume {
  width: 100%;
  height: 100%;
  background-repeat:no-repeat;
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
}
</style>
