<template>
  <div id="detail_bottom_bar">
    <div class="bottom_left">
      <div class="service">
        <i class="icon"></i>
        <span>客服</span>
      </div>
      <div class="shop">
        <i class="icon"></i>
        <span>店铺</span>
      </div>
      <div class="collect">
        <i class="icon"></i>
        <span>收藏</span>
      </div>
    </div>
    <div class="bottom_right">
      <div class="cart" @click="addToCart">
        加入购物车
      </div>
      <div class="buy">
        购买
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name:'DetailBottomBar',
  components: {
    
  },
  data() {
    return { 
     
    }
  },
  methods: {
    addToCart(){
    this.$emit('addCart')
    }
  }
}
</script>

<style>
#detail_bottom_bar{
  background-color: white;
  height: 49px;
  position: fixed;
  display: flex;
  bottom:0px;
  right: 0px;
  left: 0px;
  z-index: 1000;
}
.bottom_left {
  display: flex;
  flex: 1;
}
.bottom_left > div {
  flex: 1;
  text-align: center;
  border-right: 0.04rem solid rgba(128, 128, 128, 0.2);
}
.bottom_left .icon {
  display: block;
  background: url("~assets/img/detail/detail_bottom.png") 0 0/100%;
  width: 15px;
  height: 15px;
  margin: 2px auto;
}
.service .icon{
   background-position: 0 -17px;
}
.shop .icon {
  background-position: 0 -35px;
}
.bottom_right {
  display: flex;
  flex: 1;
}
.bottom_right > div {
  flex: 1;
  line-height: 49px;
  text-align: center;

}
.cart {
  background-color: rgb(255, 174, 0);
}
.buy {
  background-color: var(--color-tint);
  color: white;
}
</style>
