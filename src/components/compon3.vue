<template>
  <div class="info">
    <h1>作品集/Profile</h1>
    <transition
      :duration="{ enter: 2500, leave: 1500 }"
      enter-active-class="animated fadeInRight">
      <div class="cont"  v-if="show">
        <el-row :gutter="20">
          <template v-for="item in profiles">
            <el-col :key="item.name" :span="12" :xs="24">
              <div class="item">
                <h2 v-text="item.name"></h2>
                <p v-text="'技术栈: ' + item.skills"></p>
                <p v-text="item.content"></p>
                <p v-text="'github地址: ' + item.github"></p>
              </div>
            </el-col>
          </template>
        </el-row>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  data () {
    return {
      show: false,
      profiles: [
        {
          name: '电商代理商城(learn)',
          skills: 'vue vue-cli vue-router vuex axios qiniu echart element-ui mavon-editor',
          content: '这个代理商城项目有完整的前后端页面，基本实现了商城的所有功能，用户登录注册，状态管理，商品分类展示搜索，用户购买、发货，后端页面也完全实现了网站整体设置，用户统计，购买统计，商品管理、用户管理、订单管理等的功能！',
          github: 'https://github.com/lyttonlee/learn'
        },
        {
          name: '电商代理商城服务端(express-server)',
          skills: 'node express mongoose mongodb3.4 express-promise-router async/await语法',
          content: '这是代理商城项目的服务端，express框架,数据库为mongodb3.4,使用async/await语法，使用express-promise-router统一捕获error，七牛云作为图片存储空间，开发中用到RoBo 3T,postman等工具，功能也完全响应代理商城客户端!',
          github: 'https://github.com/lyttonlee/express-server-for-learn'
        },
        {
          name: 'MarkDown文章编辑器',
          skills: 'electron vue vue-cli vue-router axios qiniu nedb element-ui mavon-editor',
          content: '本软件只要配置七牛云信息,文章中插入的图片将自动上传至用户的七牛云空间，软件使用nedb本地数据库，使用electron打包为各平台的应用!',
          github: 'https://github.com/lyttonlee/md-editor'
        },
        {
          name: '火焰纹章if人物升级模拟',
          skills: 'electron vue vue-cli element-ui',
          content: '这是一个辅助Demo，可以看成是火焰纹章if这款游戏的小插件，功能就是模拟游戏人物升级时的能力提升（因为是随机数成长，每次提升的能力都不一样），得出期望数值，虽然没啥意义，但很能体现程序员思维，会去实现某些无聊的日常小需求!',
          github: 'https://github.com/lyttonlee/if'
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
    width: 90%;
    .item {
      background-color: rgba(59, 123, 13, 0.2);
      padding: 10px;
      border-radius: 15px;
      margin: 10px auto;
      @media screen and (max-width: 768px) {
        padding: 5px;
        margin: 5px auto;
      }
      &:hover {
        border-radius: 25px;
        background-color: rgba(10, 135, 87, 0.3);
      }
      p {
        text-align: left;
        text-indent: 28px;
        font-size: 1.1rem;
        line-height: 1.2;
        @media screen and (max-width: 768px) {
          text-indent: 12px;
          font-size: 0.7rem;
          line-height: 1.1;
        }
      }
    }
  }
}
</style>
