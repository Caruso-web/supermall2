<template>
<div id="Car">
  <new-bar class="car-nav" ><div slot="center">购物街({{carLength}})</div></new-bar>
  <car-list></car-list>
  <car-list-bottom></car-list-bottom>
</div>
</template>

<script>
import NewBar from 'components/common/navbar/NewBar'
import carList from './childcar/carList'
import carListBottom from './childcar/carListBottom'



import {mapGetters} from 'vuex'

export default {
  name:'Car',
  components: {
    NewBar,
    carList,
    carListBottom
  },
  computed: {
  ...mapGetters([
    'carLength','carList'
  ])
  }
}
</script>

<style>
#Car{
  background: white;
}
.car-nav{
  background-color: var(--color-tint);
  color:white;
}
</style>
