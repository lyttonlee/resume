<template>
  <div class="info">
    <h1>技术栈/Skills</h1>
    <transition
      :duration="{ enter: 2500, leave: 1500 }"
      leave-active-class="animated fadeOutRight"
      enter-active-class="animated fadeInLeft">
      <div class="cont"  v-if="show">
        <template v-for="skill in skills">
          <el-row :gutter="20" :key="skill.name">
            <el-col :span="8">
              <div class="left" :style="{backgroundColor: `${skill.background}`}">
                <h2>{{skill.name}}</h2>
              </div>
            </el-col>
          <el-col :span="16">
              <el-row :gutter="10">
                <template v-for="child in skill.child">
                  <el-col :span="12"  :key="child.name">
                    <div class="right" :style="{backgroundColor: child.background}">
                      <h3>{{child.name}}</h3>
                    </div>
                  </el-col>
                </template>
              </el-row>
          </el-col>
        </el-row>
        </template>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  // let randomcolor = rgba()
  data () {
    return {
      show: false,
      skills: [
        {
          name: '前端',
          background: 'rgba(29, 218, 61, 0.2)',
          child: [
            {name: 'Vue', background: 'rgba(29, 218, 61, 0.2)'},
            {name: 'VueRouter', background: 'rgba(29, 218, 61, 0.2)'},
            {name: 'Vuex', background: 'rgba(29, 218, 61, 0.2)'},
            {name: 'axios', background: 'rgba(29, 218, 61, 0.2)'}
          ]
        },
        {
          name: '服务端',
          background: 'rgba(211, 184, 30, 0.2)',
          child: [
            {name: 'NodeJs', background: 'rgba(211, 184, 30, 0.2)'},
            {name: 'mongoose', background: 'rgba(211, 184, 30, 0.2)'},
            {name: 'express', background: 'rgba(211, 184, 30, 0.2)'},
            {name: 'ES6', background: 'rgba(211, 184, 30, 0.2)'}
          ]
        },
        {
          name: '工具',
          background: 'rgba(232, 13, 24, 0.2)',
          child: [
            {name: 'Git', background: 'rgba(232, 13, 24, 0.2)'},
            {name: 'WebPack', background: 'rgba(232, 13, 24, 0.2)'},
            {name: 'Ubuntu', background: 'rgba(232, 13, 24, 0.2)'},
            {name: 'VS Code', background: 'rgba(232, 13, 24, 0.2)'}
          ]
        }
      ]
    }
  },
  methods: {
    timeout () {
      setTimeout(() => {
        this.show = true
      }, 1000)
    }
  },
  mounted () {
    this.timeout()
  }
}
</script>

<style lang="less" scoped>
@import '../less/index.less';
.info {
  .info;
  .cont {
    .cont;
    .left {
      margin: 10px auto;
      width: 100%;
      height: 160px;
      // background-color: rgba(211, 184, 30, 0.2);
      line-height: 160px;
    }
    .right {
      height: 70px;
      // background-color: rgba(232, 13, 24, 0.2);
      line-height: 70px;
    }
  }
}
</style>
