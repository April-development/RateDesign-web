<template>
  <user-search-input />
</template>
<script>
import UserSearchInput from '@/components/user-search-input'
export default {
  name: 'Users',
  components: { UserSearchInput },
  layout: 'admin',
}
</script>
