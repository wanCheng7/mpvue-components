<template>
  <div class="home_page" >
    <swiper-banner :list="imgUrls" :activeIndex="activeIndex" @change="bannerChangeFn" />

    <p class="test">针对3D生物打印设备通常无法实现多喷头切换的问题，研发一种3D生物打印设备。希望该设备包括以下模块：喷头架、喷头体和抓取等必要装置，可以实现自动三维扫描矫正，通过三维打印工艺将矫形器数字三维模型打印成形。希望该3D生物打印设备能广泛应用于人体器官打印等前沿领域。</p>
    <p class="test2">我是测试文字，啊哈哈</p>

  </div>
</template>

<script>
import swiperBanner from '@/components/banner'

export default {
  data () {
    return {
      imgUrls: [
        {url: 'http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg', tit: '创新者在线-专注于企业科技价值'},
        {url: 'http://img06.tooopen.com/images/20160818/tooopen_sy_175866434296.jpg', tit: '222创新者在线-专注于企业科技价值'},
        {url: 'http://img06.tooopen.com/images/20160818/tooopen_sy_175833047715.jpg', tit: '324创新者在线'}
      ],
      activeIndex: 0,
    }
  },
  components: {
    swiperBanner
  },
  mounted () {

  },
  methods: {
    bannerChangeFn (data) {
      this.activeIndex = data;
    }
  }
}
</script>

<style lang="scss">
  .test {
     display: -webkit-box; // 这里和单行省略设置不同
    font-size:28rpx;
    color:#000000;
    line-height: 40rpx;
    word-break: break-all;
    -webkit-box-orient: vertical; // 这里和单行省略设置不同
    -webkit-line-clamp:2; // 第二行显示不下才显示省略号
    overflow: hidden; // 超出隐藏
    text-overflow:ellipsis; // 超出省略
  }
  .test2 {font-size: 1rem;}
</style>
