<template>
  <div class="tab-bar-item" @click="btnClick">
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-active"></slot></div>
    <div :style="activeStyle"><slot name="item-text"></slot></div>
    
  </div>
</template>

<script>

export default {
  name: 'tabBarItem',

  props:{
      path:String,
      activeColor:{
          type:String,
          default:'red'
      }
  },
  data(){
      return{
          //isActive:true
      }
  },
  methods:{
      btnClick(){
          this.$router.push(this.path).catch(err=>err)

      }
  },
  computed:{
      isActive() {
       return this.$route.path.indexOf(this.path) !== -1
      },
      activeStyle(){
          return  this.isActive?{color:this.activeColor} :{}
      }
  }
}
</script>

<style>

 .tab-bar-item{
   flex: 1;
   height: 49px;
   text-align: center;
  
  

 }
 .tab-bar-item img{
   width: 24px;
   height: 24px;
 }

</style>
