<template>
  <div class="header">
    <div class="logo">后台管理系统</div>
    <div class="user-info">
      <el-dropdown trigger="click" @command="handleCommand">
                <span class="el-dropdown-link">
                  <i class="iconfont icon-geren"></i>
                    admin
                </span>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item command="loginout">退出</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        name: 'admin'
      }
    },
    computed:{
      username(){
        let username = localStorage.getItem('ms_username');
        return username ? username : this.name;
      }
    },
    methods:{
      handleCommand(command) {
        if(command == 'loginout'){
          localStorage.removeItem('ms_username')
          this.$router.push('/login');
        }
      }
    }
  }
</script>
<style scoped>
  .header {
    position: relative;
    box-sizing: border-box;
    width: 100%;
    height: 70px;
    padding: 0;
    margin:0;
    font-size: 22px;
    line-height: 70px;
    color: #fff;
    background-color: #242f42;
  }
  .header .logo{
    float: left;
    width:250px;
    text-align: center;
  }
  .user-info {
    float: right;
    padding-right: 100px;
    font-size: 16px;
    color: #fff;
  }
  .user-info .el-dropdown-link{
    position: relative;
    display: inline-block;
    padding-left: 50px;
    color: #fff;
    cursor: pointer;
    vertical-align: middle;
  }
</style>
