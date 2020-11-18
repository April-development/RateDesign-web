<template>
  <div class="table">
    <a-table :columns="columns" :data-source="data">
      <div slot="action">
        <a-button>Разблокировать</a-button>
        <a-button>Написать</a-button>
      </div>
    </a-table>
  </div>
</template>

<script>
import { Table, Button } from 'ant-design-vue'

const columns = [
  {
    title: 'Имя',
    dataIndex: 'name',
    key: 'name',
  },
  {
    title: 'Дата блокировки',
    dataIndex: 'date',
    key: 'date',
  },
  {
    title: 'Причина блокировки',
    dataIndex: 'reason',
    key: 'reason',
  },
  {
    title: 'Действия',
    key: 'action',
    fixed: 'right',
    scopedSlots: { customRender: 'action' },
  },
]

const data = [
  {
    key: '1',
    name: 'John Brown',
    date: 123123,
    reason: 'Свинопас',
  },
  {
    key: '2',
    name: 'Jim Green',
    date: 123123,
    reason: 'Свинопас',
  },
  {
    key: '3',
    name: 'Joe Black',
    date: 123123,
    reason: 'Свинопас',
  },
]

export default {
  name: 'Blacklist',
  layout: 'admin',
  components: {
    'a-table': Table,
    'a-button': Button,
  },
  data() {
    return {
      data,
      columns,
    }
  },
}
</script>

<style scoped>
.table {
  background-color: #fff;
}
</style>
