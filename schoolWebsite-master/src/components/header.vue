<template>
  <div class="header">
    <div class="top">
      <div class="logo fl">
        <router-link to="/">
          <img src="@/assets/logo.png" alt="计算机毕业设计网">
        </router-link>
      </div>
      <div class="tel fr">咨询QQ：8888888</div>
    </div>
    <div class="menu">
      <div class="center">
        <router-link
          :to="item.link"
          v-for="(item, index) in menuLists"
          :key="index"
          :class="{'active': activeIndex === index}"
          @click.native="changeIndex(index)"
        >{{ item.title }}</router-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      menuLists: [
        {
          title: '首页',
          link: '/'
        },
        {
          title: '团队简介',
          link: 'introduction'
        },
        {
          title: '团队新闻',
          link: 'news'
        },
        {
          title: '软件开发指导',
          link: 'teaching'
        },
        {
          title: '论文撰写指导',
          link: 'professors'
        },
        {
          title: '定制说明',
          link: 'customization'
        },
        {
          title: '联系我们',
          link: 'contact'
        }
      ],
      activeIndex: 0
    }
  },
  methods: {
    changeIndex (index) {
      this.activeIndex = index
    }
  },
  watch: {
    '$route' (val) {
      this.menuLists.map((item, index) => {
        if (val.path.indexOf(item.link) !== -1) {
          this.activeIndex = index
        }
      })
    }
  }
}
</script>
<style lang="scss" scoped>
.header {
  position: relative;
  z-index: 10;
  .top {
    height: 70px;
    background-color: #409EFF;
    background: url("../assets/Group.png");
    padding: 0 70px;
    color: #fff;
    position: relative;
    overflow: hidden;
    .logo {
      a {
        display: block;
        width: 100%;
        height: 50px;
        padding-top: 10px;
      }
    }
    .tel {
      font-size: 24px;
      margin-top: 20px;
    }
  }
  .menu {
    height: 50px;
    background-color: #fff;
    box-shadow: 0 4px 4px 0 rgba(19, 59, 40, 0.25);
    text-align: center;
    .center {
      display: inline;
    }
    a {
      display: inline-block;
      height: 100%;
      line-height: 50px;
      padding: 0 35px;
      color: #409EFF;
      font-size: 18px;
      margin: 0 11px;
      &:hover,
      &.active {
        background-color: #409EFF;
        color: #fff;
      }
    }
  }
}
</style>
