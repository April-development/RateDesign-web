<template>
  <div class="reports">
    <report-card v-for="report in reports" :key="report.id" :report="report" />
  </div>
</template>

<script>
import ReportCard from '@/components/report-card'

const reports = [
  {
    photos: [
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
    ],
    description: 'Описание работы',
    id: '1',
    userName: 'Дима Бычков',
  },
  {
    photos: [
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
    ],
    description: 'Описание работы',
    id: '2',
    userName: 'Дима Бычков',
  },
  {
    photos: [
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
    ],
    description: 'Описание работы',
    id: '3',
    userName: 'Дима Бычков',
  },
  {
    photos: [
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
    ],
    description: 'Описание работы',
    id: '4',
    userName: 'Дима Бычков',
  },
  {
    photos: [
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
    ],
    description: 'Описание работы',
    id: '5',
    userName: 'Дима Бычков',
  },
  {
    photos: [
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
    ],
    description: 'Описание работы',
    id: '6',
    userName: 'Дима Бычков',
  },
  {
    photos: [
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
    ],
    description: 'Описание работы',
    id: '7',
    userName: 'Дима Бычков',
  },
  {
    photos: [
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
    ],
    description: 'Описание работы',
    id: '8',
    userName: 'Дима Бычков',
  },
  {
    photos: [
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
      'https://picsum.photos/200/300',
    ],
    description: 'Описание работы',
    id: '9',
    userName: 'Дима Бычков',
  },
]

export default {
  name: 'Reports',
  components: { ReportCard },
  layout: 'admin',
  data() {
    return {
      reports,
    }
  },
}
</script>

<style scoped>
.reports {
  display: flex;
  flex-wrap: wrap;
  background-color: #fff;
}
</style>
