<template>
  <div class="wrapper">
    <v-head></v-head>
    <v-sidebar></v-sidebar>
    <div class="content">
      <transition name="move" mode="out-in"><router-view></router-view></transition>
    </div>
  </div>
</template>

<script>
  import vHead from '@/components/header';
  import vSidebar from '@/components/sidebar';
  export default {
    components:{
      vHead, vSidebar
    }
  }
</script>
<style>
  .wrapper{
    width:100%;
    height:100%;
    overflow: hidden;
  }
  .content{
    background: none repeat scroll 0 0 #fff;
    position: absolute;
    left: 220px;
    right: 0;
    top: 70px;
    bottom:0;
    width: auto;
    padding:40px;
    box-sizing: border-box;
    overflow-y: scroll;
  }
</style>

