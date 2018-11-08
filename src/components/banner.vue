<template>
  <swiper class="swiper_class" :indicator-dots="indicatorDots"
	  :autoplay="autoplay" :interval="interval" :duration="duration" :circular="circular" @change="bannerChangeFn">
	  <block v-for="(item, index) in list" :key="index" >
	    <swiper-item >
	      <div class="img_box">
	        <image :src="item.url" class="slide-image" width="355" height="150"/>
	        <div class="text_box row-between">
	          <p class="tit">{{ item.tit }}</p>
	          <p class="dot_list row-end">
	            <span class="slot" v-for="(item, index_) in list" :key="index_" :class="{'active': index_ == activeIndex}"></span>
	          </p>
	        </div>
	      </div>
	    </swiper-item>
	  </block>
	</swiper>
</template>

<script>
export default {
  props: {
  	list: {
  		type: Array,
      default: []
  	},
    activeIndex: {
      type: Number,
      default: 0
    },
  	indicatorDots: {   //是否显示面板指示点
  		type: Boolean,
  		default: false
  	},
  	autoplay: {
  		type: Boolean,
  		default: false
  	},
  	interval: {
  		type: Number,
  		default: 5000
  	},
  	duration: {
  		type: Number,
  		default: 1000
  	},
    circular: {  //衔接滑动
      type: Boolean,
      default: true
    }
  },
  methods: {
  	bannerChangeFn (e) {
      let index = e.mp.detail.current;
      this.$emit('change', index)
  	}
  }
}
</script>

<style lang="scss">
	.swiper_class {
    width: 100%; height: 450px;
    .img_box {
      position: relative; width: 100%; height: 100%;
      image {width: 100%;}
      .text_box {
        position: absolute; bottom: 0; left: 0; width: 100%; height: 80px; line-height: 80px; background: rgba(0,0,0,.5);
        .tit {color: #fff; font-size: 28px; padding-left: 30px;}
        .dot_list {
          width: 120px; height: 16px; margin-right: 30px;
          .slot {width: 16px; height: 16px; border-radius: 50%; background: #fff; opacity: 0.4; margin-left: 16px; display: inline-block;}
          .active {opacity: 0.8;}
        }
      }
    }
  }
</style>
