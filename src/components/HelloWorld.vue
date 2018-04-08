<template>
  <div
  class="resume"
  @mousewheel="mouse"
  :style="{
    backgroundImage:`url(${img})`,
    height: `${clientHeight}`
  }">
    <transition
      :duration="{ enter: 1500, leave: 0 }"
      enter-active-class="animated tada">
      <div class="section" v-if="init === 1">
        <div class="sec">
          <h3>111111111111</h3>
          <p>adjsalkjhdsakhdksajhdkasd
            asdsadhslakjdasl
          </p>
        </div>
      </div>
    </transition>
    <transition
      :duration="{ enter: 1500, leave: 0 }"
      enter-active-class="animated tada">
      <div class="section" v-if="init === 2">
        <div class="sec">
          <h3>2222222222222</h3>
          <p>adjsalkjhdsakhdksajhdkasd
            asdsadhslakjdasl
          </p>
        </div>
      </div>
    </transition>
    <transition
      :duration="{ enter: 1500, leave: 2800 }"
      enter-active-class="animated zoomin"
      leave-active-class="animated bounceOutRight">
      <div class="section" v-if="init === 3">
        <div class="sec">
          <h3>33333333333333</h3>
          <p>adjsalkjhdsakhdksajhdkasd
            asdsadhslakjdasl
          </p>
        </div>
      </div>
    </transition>
    <transition
      :duration="{ enter: 1500, leave: 2800 }"
      enter-active-class="animated tada"
      leave-active-class="animated bounceOutRight">
      <div class="section" v-if="init === 4">
        <div class="sec">
          <h3>44444444444444</h3>
          <p>adjsalkjhdsakhdksajhdkasd
            asdsadhslakjdasl
          </p>
        </div>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
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
    .position;
    .sec {
      width: 100%;
    }
  }
}
</style>
