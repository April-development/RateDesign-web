<template>
  <Card class="card">
    <Modal
      v-model="visible"
      title="Заблокировать работу"
      ok-text="Заблокировать"
      cancel-text="Отмена"
      @ok="handleOk"
    >
      <a-textarea placeholder="Причина блокировки" />
    </Modal>
    <Carousel class="carousel">
      <img
        v-for="photo in report.photos"
        :key="photo.id"
        :src="photo"
        :alt="photo.description"
      />
    </Carousel>
    <template slot="actions" class="ant-card-actions">
      <Icon key="check" type="check" />
      <Icon key="stop" type="stop" @click="showModal" />
    </template>
    <nuxt-link :to="'/admin/users/' + report.id">
      <CardMeta :title="report.userName" :description="report.description" />
    </nuxt-link>
  </Card>
</template>

<script>
import { Card, Modal, Carousel, Icon } from 'ant-design-vue'

export default {
  name: 'ReportCard',
  components: {
    Card,
    Carousel,
    Modal,
    Icon,
    CardMeta: Card.Meta,
  },
  props: {
    report: {
      photos: Array,
      description: String,
      userName: String,
      id: String,
    },
  },
  data() {
    return {
      visible: false,
    }
  },
  methods: {
    showModal() {
      this.visible = true
    },
    handleOk() {
      this.visible = false
    },
  },
}
</script>

<style scoped>
.card {
  width: 300px;
  margin: 16px;
}

.carousel {
  margin-bottom: 20px;
}

img {
  max-width: 300px;
  max-height: 300px;
}
</style>
