<template>
  <div>
    <a-auto-complete
      :data-source="usernames"
      class="input"
      placeholder="Введите имя пользователя"
      :filter-option="filterOption"
      @select="onSelect"
    />
  </div>
</template>

<script>
import { AutoComplete } from 'ant-design-vue'

const usernames = [
  'Дима Бычков',
  'Саша Заверняев',
  'Никита Брюзгин',
  'Ваня Иван',
  'Ник',
  'Витлес',
]
export default {
  name: 'UserSearchInput',
  components: { 'a-auto-complete': AutoComplete },
  layout: 'administration',
  data() {
    return {
      usernames,
    }
  },
  methods: {
    filterOption(input, option) {
      return option.componentOptions.children[0].text
        .toUpperCase()
        .includes(input.toUpperCase())
    },
    onSelect(user) {
      this.routeTo(user)
    },
    routeTo(user) {
      // TODO сделать нормальный роут
      const id = user === 'Дима Бычков' ? '123' : '456'
      this.$nuxt.$router.replace({ path: `/admin/users/${id}` })
    },
  },
}
</script>

<style scoped>
.input {
  width: 100%;
}
</style>
