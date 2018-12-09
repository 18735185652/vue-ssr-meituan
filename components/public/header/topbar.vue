<template>
  <el-row
    :gutter="0"
    class="m-header">
    <el-col :span="5">
      <div class="grid-content bg-purple">
        <geo/>
      </div>
    </el-col>
    <el-col :span="5">
      <div class="grid-content bg-purple">
        <user/>
      </div>
    </el-col>
    <el-col :span="14">
      <div class="grid-content bg-purple">
        <nav-bar/>
      </div>
    </el-col>
  </el-row>
</template>
<script>
  import Geo from "./geo.vue"
  import User from "./user.vue"
  import NavBar from "./nav.vue"
  export default{
      components:{
          Geo,
          User,
          NavBar
      }
  }
</script>
<style lang = "scss">

</style>
