<template>
  <div class="page-index">
    <el-row>
      <el-col :span="5">
        <e-menu />
      </el-col>
      <el-col :span="19">
        <banner/>
      </el-col>
    </el-row>
    <el-row :span="24">
      3
    </el-row>

  </div>
</template>

<script>
import EMenu from "@/components/index/menu.vue"
import banner from "@/components/index/life.vue"
export default {
  components: {
    EMenu,
    banner
  }
}
</script>

<style lang="scss">
@import "@/assets/css/index/index.scss";

</style>
