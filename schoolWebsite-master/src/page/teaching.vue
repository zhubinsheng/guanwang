<template>
  <div class="teaching common-box">
    <div class="w">
      <div class="menu">
        <span v-for="(item, index) in menuLists" :key="index">
          <a href="javascript:;" @click="getContent(index)" :class="{'active': activeIndex === index}">{{ item }}</a>
        </span>
      </div>

      <br>
      <br>
      <br>
      <div class="title">最新java毕业设计</div>
      <br>
      <br>
      <hr style=" height:2px;border:none;border-top:2px dotted #66b1ff;" />
      <br>
      <br>
      <br>
      <br>
      <br>
      <div class="lists clearfix">
          <div class="list fl" v-for="(item, index) in listsArr" :key="index">
            <div class="list-poster">
              <a href="javascript:;" @click="toDetail(index)">
                <img :src="item.poster" alt>
                <div class="list-brief">{{ item.brief }}</div>
              </a>
              <hr style=" height:2px;border:none;border-top:2px dotted #185598;" />
            </div>
            <div class="list-msg">
              <div class="list-title ellipsis">{{ item.title }}</div>
              <div class="list-info clearfix">
                <span class="fl">{{ item.time }}</span>
                <a class="fr" href="javascript:;" @click="toDetail(index)">查看详情</a>
              </div>
            </div>
          </div>
        </div>
        <div class="loadmore" @click="loadmore">加载更多</div>
      </div>

      <<!--div class="title">私募股权投资（PE/VC）与资本战略董事长研修班</div>
      <div class="main">
        <div class="content" v-html="content"></div>
        <div class="form">
          <div class="form-title">在线报名</div>
          <el-form ref="form" :model="form" :rules="rules" class="form-content">
            <el-form-item prop="content">
              <el-select v-model="form.content" placeholder="请选择报名内容">
                <el-option label="私募股权投资（PE/VC）与资本战略董事长研修班" value="shanghai"></el-option>
                <el-option label="私募股权投资（PE/VC）与资本战略董事长研修班" value="beijing"></el-option>
              </el-select>
            </el-form-item>
            <el-form-item prop="name">
              <el-input v-model="form.name" placeholder="请输入您的姓名"></el-input>
            </el-form-item>
            <el-form-item prop="tel">
              <el-input v-model="form.tel" placeholder="请输入您的手机号码"></el-input>
            </el-form-item>
            <el-form-item prop="company">
              <el-input v-model="form.company" placeholder="请输入您的公司名称"></el-input>
            </el-form-item>
            <el-form-item class="last">
              <el-button type="primary" @click="onSubmit('form')">立即提交</el-button>
            </el-form-item>
          </el-form>
        </div>
        <div class="content" v-html="content"></div>
      </div>-->
    </div>

</template>
<script>
export default {
  data () {
    return {
      listsArr: [
        {
          poster: './static/images/1.png',
          brief: '基于C/S模式即时聊天系统RC设计与实现(精品)☆(含任务书,开题报告,中期检查表,毕业论文说明书21000字,程序代码)  摘  要网络通信在当今信息社会中起着不可或缺的作用 ，人们可以利用网络通信技术进行即时的信息交流。',
          time: '2018-04-04'
        },
        {
          poster: './static/images/2.png',
          brief: '\n' +
          'Java实现蜘蛛纸牌设计\n' +
          'Java实现蜘蛛纸牌设计(任务书,外文翻译,毕业论文23000字,论文源代码,答辩PPT)摘  要蜘蛛纸牌的每一代的window的系统都有，同时也时一款很受用户喜欢的休闲类游戏，很多人都喜欢玩蜘蛛纸牌。本人做的蜘蛛纸牌游戏开发理念是基于window 7操作系统中的蜘蛛纸牌游戏。',
          time: '2018-04-04'
        },
        {
          poster: './static/images/1.png',
          brief: '基于B/S的企业报表管理系统(JavaEE,Oracle)(任务书,文献综述,外文翻译,毕业论文19000字,程序代码,答辩PPT)摘 要随着计算机应用的发展，信息技术在企业中发挥着越来越重要的作用。要在现代社会激烈的企业竞争中处于不败之地，就必须不断加强内部管理，加强信息化建设。',
          time: '2018-04-04'
        },
        {
          poster: './static/images/2.png',
          title: '阳山智谷EMBA总裁高级研修班 M38班课课程',
          brief: '北清智库商学院互联网导师喻旭老师为同学们带来了«新零售创新战略与路径设计»，从产业的高度，用户的角…',
          time: '2018-04-04'
        },
        {
          poster: './static/images/1.png',
          title: '阳山智谷【金融EMBA】三月课程纪实',
          brief: '北清智库商学院互联网导师喻旭老师为同学们带来了«新零售创新战略与路径设计»，从产业的高度，用户的角…',
          time: '2018-04-04'
        },
        {
          poster: './static/images/2.png',
          title: '阳山智谷EMBA总裁高级研修班 M38班课课程',
          brief: '北清智库商学院互联网导师喻旭老师为同学们带来了«新零售创新战略与路径设计»，从产业的高度，用户的角…',
          time: '2018-04-04'
        },
        {
          poster: './static/images/1.png',
          title: '4月14-15日互联网EMBA总裁研修班课程课程',
          brief: '北清智库商学院互联网导师喻旭老师为同学们带来了«新零售创新战略与路径设计»，从产业的高度，用户的角…',
          time: '2018-04-04'
        },
        {
          poster: './static/images/2.png',
          title: '阳山智谷EMBA总裁高级研修班 M38班课课程',
          brief: '北清智库商学院互联网导师喻旭老师为同学们带来了',
          time: '2018-04-04'
        },
        {
          poster: './static/images/1.png',
          title: '阳山智谷【金融EMBA】三月课程纪实',
          brief: '北清智库商学院互联网导师喻旭老师为同学们带来了«新零售创新战略与路径设计»，从产业的高度，用户的角…',
          time: '2018-04-04'
        },
        {
          poster: './static/images/2.png',
          title: '阳山智谷EMBA总裁高级研修班 M38班课课程',
          brief: '北清智库商学院互联网导师喻旭老师为同学们带来了«新零售创新战略与路径设计»，从产业的高度，用户的角…',
          time: '2018-04-04'
        },
        {
          poster: './static/images/1.png',
          title: '阳山智谷【金融EMBA】三月课程纪实',
          brief: '北清智库商学院互联网导师喻旭老师为同学们带来了«新零售创新战略与路径设计»，从产业的高度，用户的角…',
          time: '2018-04-04'
        },
        {
          poster: './static/images/2.png',
          title: '阳山智谷EMBA总裁高级研修班 M38班课课程',
          brief: '北清智库商学院互联网导师喻旭老师为同学们带来了«新零售创新战略与路径设计»，从产业的高度，用户的角…',
          time: '2018-04-04'
        }
      ],
      menuLists: ['java毕业设计', 'python毕业设计', '安卓毕业设计', '前端毕业设计', '大数据毕业设计'],
      activeIndex: 0,
      content: '&nbsp;&nbsp;&nbsp;&nbsp;中国经济经历30余年高速发展，早已成为世界第二大经济体，未来十年或可跃升为第一大经济体，到2020年将完成全面小康社会的建设，也就意味着中国经济与社会完成第一阶段发展目标；阳山智谷正是基于对中国社会全面转型的关键时刻的深度研究，由北京大学本、硕、博毕业的教授、企业家、专业领域专家等共同发起成立。力求伴随中国经济转型的关键十年，成功跻身中国十大商学院之列。<br><br><br>&nbsp;&nbsp;&nbsp;&nbsp;阳山智谷商学院研究发现，经济与社会全面转型的今天，传统市场驱动型的业务模式逐渐发生变化，社会对企业家的各项能力要求逐步提高，尤其是知识技能的要求有了显著的提升，而传统的企业家大多缺乏系统性的经济学与商学教育，这就需要企业家不断的学习来适应社会变化的需要。阳山智谷因势利导提出了“一切都在变，唯有学习不能变！”的学习口号，号召当代企业家主动加强个人的文化素质提升，用更强大更全面的知识武装自己，达到有效整合资源所应该匹配的知识背景，提升个人和企业的核心竞争能力。<br><br><br>&nbsp;&nbsp;&nbsp;&nbsp;阳山智谷商学院课程体系设计，引领企业家关注企业系统性的再生能力，深入研究企业所处的行业或产业结构与趋势，深入研究区域经济特点与区域产业结构与特性，系统性研究企业经营和管理，全面掌握资本市场的逻辑与规则，同时理解政策与政治对社会、经济和企业经营所产生的影响与变化，阳山智谷商学院的系统性课程体系正是以此为基础进行全面细致的设计，满足各阶段企业家学习需求，实现“让培训回归培训，让教育回归教育”的办学情怀！最终引导企业家摒弃以市场驱动为导向的“老板思维”，真正具备新时代“企业家思维”、“投资家思维”、“政治家思维”从而实现科学经营与科学管理企业，让企业在全面转型档口立于不败之地。 我们有理由相信：阳山智谷商学院用“十年时间做成一件事”的专注精神，以“对己：知行厚德，对人：互溶共进，对事：拼搏极致”的核心价值为指引，凭借北大人“思想自由、兼容并包”的文化特性，我们有能力以新格局、新思维和新对策为企业家EMBA教育事业发展写下精彩的一页。',
      form: {
        name: '',
        content: '',
        company: '',
        tel: ''
      },
      rules: {
        name: [
          { required: true, message: '请输入您的姓名', trigger: 'blur' }
        ],
        content: [
          { required: true, message: '请选择报名内容', trigger: 'change' }
        ],
        tel: [
          { required: true, message: '请输入您的手机号码', trigger: 'blur' }
        ],
        company: [
          { required: true, message: '请输入您的公司名称', trigger: 'blur' }
        ]
      }
    }
  },
  methods: {
    getContent (index) {
      this.activeIndex = index
    },
    onSubmit (formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert('submit!')
        } else {
          console.log('error submit!!')
          return false
        }
      })
    }
  }
}
</script>
<style>
.teaching .el-form-item.last {
  margin-bottom: 0;
}
.teaching .el-select {
  width: 100%;
}
.teaching .el-button--primary {
  width: 100%;
  background-color: #133B28;
  border-color: #133B28;
  letter-spacing: 3.5px;
}
</style>
<style lang="scss" scoped>
.teaching {
  .w {
    padding: 40px 100px 0;
    .title {
      margin-top: 40px;
      padding: 0;
      letter-spacing: 0;
    }
    .menu {
      height: 40px;
      line-height: 40px;
      width: 1000px;
      border-bottom: 2px solid #133B28;
      padding: 0 80px;
      span {
        display: inline-block;
        width: 20%;
        text-align: center;
        a {
          &.active {
            font-size: 18px;
            font-weight: bold;
          }
        }
      }
    }
    .main {
      padding: 50px;
      .form {
        width: 467px;
        border: 1px solid #133B28;
        border-radius: 10px;
        margin: 50px auto 86px;
        overflow: hidden;
        box-shadow: 0 0 8px 0 rgba(19,59,40,0.25);
        .form-title {
          height: 50px;
          line-height: 50px;
          background-color: #133B28;
          color: #FFFFFF;
          letter-spacing: 3px;
          padding-left: 40px;
        }
        .form-content {
          padding: 30px;
        }
      }
    }
  }
}
</style>
