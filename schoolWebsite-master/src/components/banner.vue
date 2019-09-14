<template>
<el-card shadow="always">
  <div class="banner">
    <el-carousel
      height="350px"
      type="card"
      :indicator-position="indicatorStatus"
      :interval="5000"
    >
      <el-carousel-item
        v-for="(item, index) in bannerLists"
        :key="index"
        :style="`background: url(${item}) no-repeat center`"
      ></el-carousel-item>
    </el-carousel>
  </div>
</el-card>
</template>
<script>
export default {
  data () {
    return {
      bannerLists: ['./static/images/banner.png', './static/images/banner.png', './static/images/banner.png', './static/images/banner.png'],
      indicatorStatus: 'inside'
    }
  },
  created () {
    this.indicatorStatus = this.bannerLists.length > 1 ? 'inside' : 'none'
  }
}
</script>
<style>
.banner .el-carousel__button {
  opacity: 1;
  width: 12px;
  height: 12px;
  border-radius: 100%;
  background-color: #afafaf;
}
.banner .el-carousel__indicator.is-active button {
  background-image: linear-gradient(-180deg, #409EFF 0%, #409EFF 100%);
}
.banner .el-carousel__arrow {
  font-size: 20px;
  background-color: rgba(31, 45, 61, 0.3);
}
</style>
