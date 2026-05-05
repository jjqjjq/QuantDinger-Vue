<template>
  <div class="jjq-test-page">
    <div class="page-header">
      <h2 class="page-title">
        <a-icon type="experiment" />
        <span>{{ $t('menu.jjqTest') }}</span>
      </h2>
    </div>

    <a-card>
      <div class="test-content">
        <h3>{{ $t('jjqTest.welcome') }}</h3>
        <p>{{ $t('jjqTest.description') }}</p>

        <a-divider />

        <a-row :gutter="16">
          <a-col :span="12">
            <a-statistic title="测试数据 1" :value="100" suffix="USD" />
          </a-col>
          <a-col :span="12">
            <a-statistic title="测试数据 2" :value="250" suffix="USDT" />
          </a-col>
        </a-row>

        <a-divider />

        <a-button type="primary" @click="handleTest">
          <a-icon type="play-circle" />
          {{ $t('jjqTest.testButton') }}
        </a-button>

        <a-divider />

        <a-alert
          v-if="message"
          :message="message"
          :type="alertType"
          showIcon
          closable
          @close="message = ''"
        />
      </div>
    </a-card>
  </div>
</template>

<script>
export default {
  name: 'JJQTest',
  data () {
    return {
      message: '',
      alertType: 'success'
    }
  },
  methods: {
    handleTest () {
      this.message = this.$t('jjqTest.testSuccess')
      this.alertType = 'success'
    }
  }
}
</script>

<style scoped>
.jjq-test-page {
  padding: 24px;
}

.page-header {
  margin-bottom: 24px;
}

.page-title {
  font-size: 24px;
  font-weight: 500;
  color: rgba(0, 0, 0, 0.85);
  margin: 0;
}

.page-title span {
  margin-left: 8px;
}

.test-content {
  min-height: 400px;
}

.test-content h3 {
  margin-bottom: 16px;
}
</style>
