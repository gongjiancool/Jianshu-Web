<template>
  <div>
    <div>
      <br>
      <div>
        <b-img rounded src="//cdn2.jianshu.io/assets/web/recommend-collection-58f8968955ecbeb8f8f3b4cd95ec76be.png" fluid alt="Responsive image" />
      </div>
      <br>
      <div>
        <b-nav tabs>
          <b-nav-item ><router-link to="tuijian"><span class="color">推荐</span></router-link></b-nav-item>
          <b-nav-item><span class="color">热门</span></b-nav-item>
          <b-nav-item><span class="color">城市</span></b-nav-item>
          <b-nav-item><span class="color">校园</span></b-nav-item>
        </b-nav>
      </div>
    </div>
    <div>
      <keep-alive>
        <router-view></router-view>
      </keep-alive>
    </div>
  </div>


</template>

<script>
  import vCollection from '../common/Collection'
  export default {
    name: "Collections",
    components:{
      vCollection
    }
  }
</script>

<style scoped>
.color{
  color: #000;
}
</style>
