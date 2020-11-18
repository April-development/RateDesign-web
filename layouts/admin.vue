<template>
  <a-layout>
    <a-layout-sider class="sider">
      <admin-menu></admin-menu>
    </a-layout-sider>
    <a-layout class="layout">
      <a-layout-content class="layout-content">
        <nuxt></nuxt>
      </a-layout-content>
    </a-layout>
  </a-layout>
</template>

<script>
import { Layout } from 'ant-design-vue'
import AdminMenu from '@/components/admin-menu'

export default {
  name: 'Admin',
  components: {
    AdminMenu,
    'a-layout': Layout,
    'a-layout-content': Layout.Content,
    'a-layout-sider': Layout.Sider,
  },
}
</script>

<style scoped>
.sider {
  overflow: auto;
  height: 100vh;
  position: fixed;
  left: 0;
}

.layout {
  margin-left: 200px;
}

.layout-content {
  min-height: 100vh;
  padding: 16px;
}
</style>
