<template>
  <div id="app">
    <!--横屏提示-->
    <div class="horizontal-full">
      <div class="table-full">
        <div class="tb-m">
          <img src="@/assets/img/horizontal_tip.png" alt="">
        </div>
      </div>
    </div>
    <!--横屏提示结束-->
    <keep-alive>
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
  @media screen and (max-aspect-ratio:13/9){
    .horizontal-full{
      display: none;
    }
  }
  @media (orientation: portrait){
    .horizontal-full{
      display: none;
    }
  }
  .horizontal-full{
    position: fixed;
    width: 100%;
    height: 100%;
    background-color: #303030;
    z-index:1200;
    text-align: center;
    left: 0;
    top:0;
  }
  .table-full{
    display: table;
    width: 100%;
    height: 100%;
  }
  .tb-m{
    display: table-cell;
    width: 100%;
    height: 100%;
    vertical-align: middle;
  }
  .tb-m img{
    width: 100%;
    vertical-align: top;
  }
</style>
