<template>
  <div>
    <div class="header">
      <a-page-header :ghost="false" :title="userData.userName">
        <template slot="extra">
          <a-button key="3" type="primary"> Написать сообщение </a-button>
          <a-button key="2" type="danger"> Удалить все работы </a-button>
          <a-button key="1" type="danger">
            Заблокировать пользователя
          </a-button>
        </template>
        <a-descriptions size="small" :column="3">
          <a-descriptions-item label="Id">
            {{ userData.id }}
          </a-descriptions-item>
          <a-descriptions-item label="Всего оценок">
            {{ userData.statistic.totalRates }}
          </a-descriptions-item>
          <a-descriptions-item label="Средняя оценка">
            {{ userData.statistic.averageRate }}
          </a-descriptions-item>
          <a-descriptions-item label="Медианная оценка">
            {{ userData.statistic.medianRate }}
          </a-descriptions-item>
          <a-descriptions-item label="Последний вход">
            {{ userData.lastEntryDate }}
          </a-descriptions-item>
        </a-descriptions>
      </a-page-header>
    </div>
    <a-row type="flex" class="workList">
      <a-col
        v-for="work in userData.works"
        :key="work.publishDate"
        :span="8"
        :style="{ maxWidth: '300px' }"
      >
        <a-card class="card">
          <a-carousel class="carousel">
            <img :src="work.photos[0]" alt="" />
            <img :src="work.photos[1]" alt="" />
            <img :src="work.photos[2]" alt="" />
          </a-carousel>
          <a-card-meta :title="'Средняя оценка: ' + work.averageRate">
            <div slot="description" class="card-description">
              Дата публикации: {{ work.publishDate }}
            </div>
          </a-card-meta>
        </a-card>
      </a-col>
    </a-row>
  </div>
</template>

<script>
import {
  PageHeader,
  Button,
  Descriptions,
  Card,
  Carousel,
} from 'ant-design-vue'
import Row from 'ant-design-vue/lib/row'
import Col from 'ant-design-vue/lib/col'

export default {
  name: 'UserProfile',
  components: {
    'a-page-header': PageHeader,
    'a-button': Button,
    'a-descriptions': Descriptions,
    'a-descriptions-item': Descriptions.Item,
    'a-card': Card,
    'a-card-meta': Card.Meta,
    'a-carousel': Carousel,
    'a-row': Row,
    'a-col': Col,
  },
  props: {
    userData: {
      id: String,
      userName: String,
      lastEntryDate: String,
      works: [
        {
          photos: [String],
          publishingDate: String,
          averageRate: Number,
        },
      ],
      statistic: {
        totalRates: Number,
        averageRate: Number,
        medianRate: Number,
      },
    },
  },
}
</script>

<style scoped>
.header {
  padding-top: 16px;
}

.card {
  margin: 16px;
}

.card-description {
  margin-top: -10px;
}

.carousel {
  margin-bottom: 20px;
}
</style>
