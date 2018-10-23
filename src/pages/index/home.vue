<template>
  <div class="home_page" >
    <swiper-banner :list="imgUrls"   />
    <p>666</p>

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
    }
  },
  components: {
    swiperBanner
  },
  mounted () {

  },
  methods: {

  }
}
</script>

<style >
  
</style>
