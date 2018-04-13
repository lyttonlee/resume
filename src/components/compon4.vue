<template>
  <div class="info">
    <h1>联系我/Contact</h1>
    <transition
      :duration="{ enter: 2500, leave: 1500 }"
      enter-active-class="animated fadeInDown">
      <div class="cont"  v-if="show">
        <div class="assessment">
          <h2>自我评价</h2>
          <p>高效的自学能力,具备独立分析解决问题能力</p>
          <p>强烈的自我驱动力,只喜欢优雅的代码</p>
          <p>熟悉组件化开发，sf重度依耐性患者</p>
        </div>
        <div class="honor">
          <h2>兴趣爱好</h2>
          <p>爱读书、爱写字、爱喝茶</p>
          <p>喜欢尝试新事物</p>
        </div>
        <div class="contact">
          <h2>联系我</h2>
          <p><i class="iconfont icon-shouji"></i>  15181589155</p>
          <p><i class="iconfont icon-youxiang"></i>  lzr3278@163.com</p>
        </div>
        <div class="acount">
          <el-row>
            <template v-for="item in accounts">
              <el-col :span="6" :key="item.class">
                <div class="iconBox">
                  <a :href="item.link"><i class="iconfont iconSet" :class="item.class"></i></a>
                </div>
              </el-col>
            </template>
          </el-row>
        </div>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  data () {
    return {
      show: false,
      accounts: [
        {class: 'icon-GitHub', link: 'https://github.com/lyttonlee'},
        {class: 'icon-sf', link: 'https://segmentfault.com/u/siwuweihesi'},
        {class: 'icon-zhihu', link: 'https://www.zhihu.com/people/li-zai-rong-27/activities'},
        {class: 'icon-xinlang', link: 'https://weibo.com/1803573600/profile?topnav=1&wvr=6&is_all=1'}
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
a {
  text-decoration: none;
}
.info {
  .info;
  .cont {
    .cont;
    margin: 20px auto;
    background-color: rgba(233, 225, 225, .3);
    border-radius: 25px;
    padding: 30px 0;
    .acount {
      width: 30%;
      margin: 10px auto;
      .iconBox {
        width: 40px;
        height: 40px;
        border-radius: 20px;
        border: 1px solid rgba(9, 92, 49, .5);
        margin: 5px auto;
        background-color: rgba(13, 73, 87, 0.4);
        &:hover {
          background-color: rgba(13, 73, 87, 0.8);
        }
        .iconSet {
          font-size: 1.5rem;
          line-height: 40px;
          cursor: pointer;
          color: rgba(220, 228, 220, 0.7);
          &:hover {
            font-size: 1.8rem;
            color: rgba(220, 228, 220, 1);
          }
        }
      }
    }
  }
}
</style>
