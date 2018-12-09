<template>
  <el-container class="layout-default">
    <el-header height="auto">
      <my-header/>
    </el-header>
    <el-main>
      <nuxt/>
    </el-main>
    <el-footer height="100%">footer
    </el-footer>
  </el-container>
</template>

<script>
  import MyHeader from '@/components/public/header/index.vue'
  export default {
    components:{
      MyHeader,
    }
  }
</script>
