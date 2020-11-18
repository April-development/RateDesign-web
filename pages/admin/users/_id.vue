<template>
  <div>
    <user-search-input />
    <!--  TODO убрать временную заглушку-->
    <user-profile v-if="id === '123'" :user-data="userData" />
  </div>
</template>

<script>
import UserProfile from '@/components/user-profile'
import UserSearchInput from '@/components/user-search-input'

const Dima = {
  id: '123',
  userName: 'Дима Бычков',
  works: [
    {
      photos: [
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
      ],
      publishDate: '2017',
      averageRate: 4,
    },
    {
      photos: [
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
      ],
      publishDate: '2017',
      averageRate: 4,
    },
    {
      photos: [
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
      ],
      publishDate: '2017',
      averageRate: 4,
    },
    {
      photos: [
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
      ],
      publishDate: '2017',
      averageRate: 4,
    },
    {
      photos: [
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
        'https://picsum.photos/200/300',
      ],
      publishDate: '20178345',
      averageRate: 3,
    },
  ],
  statistic: {
    totalRates: 1231524,
    averageRate: 4,
    medianRate: 3,
  },
  lastEntryDate: '02,10,2020',
}

export default {
  name: 'Id',
  components: { UserSearchInput, UserProfile },
  layout: 'admin',
  asyncData({ params: { id } }) {
    return { id }
  },
  data() {
    return {
      userData: Dima,
    }
  },
}
</script>
