<template>
  <a-menu theme="dark" mode="inline">
    <a-menu-item key="1">
      <nuxt-link to="/admin/users">
        <a-icon type="user" />
        <span>Пользователи</span>
      </nuxt-link>
    </a-menu-item>
    <a-menu-item key="2">
      <nuxt-link to="/admin/reports">
        <a-icon type="bug" />
        <span>Жалобы</span>
      </nuxt-link>
    </a-menu-item>
    <a-menu-item key="3">
      <nuxt-link to="/admin/blacklist">
        <a-icon type="stop" />
        <span>Баны</span>
      </nuxt-link>
    </a-menu-item>
    <a-menu-item key="4">
      <nuxt-link to="/admin/stats">
        <a-icon type="bar-chart" />
        <span>Статистика</span>
      </nuxt-link>
    </a-menu-item>
  </a-menu>
</template>

<script>
import { Icon, Menu } from 'ant-design-vue'

export default {
  name: 'AdminMenu',
  components: {
    'a-menu-item': Menu.Item,
    'a-menu': Menu,
    'a-icon': Icon,
  },
}
</script>
