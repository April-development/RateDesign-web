<template>
  <div class="charts">
    <div v-for="chart in charts" :key="chart.key">
      <chart :width="750" :height="450" :data="chart" />
    </div>
  </div>
</template>

<script>
import chart from '@/components/chart'

const charts = [
  {
    label: 'Медианное время сессии',
    values: [12, 19, 3, 5, 2, 3],
    labels: [1, 2, 3, 4, 5, 6],
    key: 1,
  },
  {
    label: 'Медианное количество оценок на пользователя',
    values: [12, 19, 3, 5, 2, 3],
    labels: [1, 2, 3, 4, 5, 6],
    key: 2,
  },
  {
    label: 'Медианное количество выложенных работ',
    values: [12, 19, 3, 5, 2, 3],
    labels: [1, 2, 3, 4, 5, 6],
    key: 3,
  },
]
export default {
  name: 'Stats',
  components: { chart },
  layout: 'admin',
  data() {
    return {
      charts,
    }
  },
}
</script>

<style scoped>
.charts {
  display: flex;
  flex-wrap: wrap;
}
.charts > div {
  margin: 5px 40px;
}
</style>
