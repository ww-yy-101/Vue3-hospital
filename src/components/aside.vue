<script setup>
import TreeMenu from '../components/treeMenu.vue'
import { useRouter } from 'vue-router'
import { reactive } from 'vue'

const router = useRouter()
const menuData = reactive(router.options.routes[0].children)

const handleOpen = () => {}
const handleClose = () => {}
</script>
<template>
<el-menu
        :style="{width: '200px'}"
        active-text-color="#ffd04b"
        background-color="#545c64"
        text-color="#fff"
        default-active="2"
        class="aside-container"
        @open="handleOpen"
        @close="handleClose"
      >
      <p class="logo-lg">DIDI陪诊</p>
       <TreeMenu :index="1" :menuData="menuData"/>
      </el-menu>
</template>
<style lang="less" scoped>
  .aside-container {
  height: 100%;
  .logo-lg {
    font-size: 20px;
    text-align: center;
    height: 50px;
    line-height: 50px;
    color: #fff;
  }
}
</style>