<template>
  <div class="layout-footer">
    {{ year }} © Powered by
    <a href="https://www.baidu.com" target="_blank">Blog</a>
    <span class="record-info">
      |
      <a href="http://www.beian.miit.gov.cn">备案号</a>
    </span>
    <span v-if="showLogin" class="admin-link">
      |
      <nuxt-link to="/admin">
        后台管理
      </nuxt-link>
    </span>
  </div>
</template>

<script lang="ts">
import Vue, { PropOptions } from 'vue';
export default Vue.extend({
  props: {
    showLogin: {
      type: Boolean,
      default: false
    } as PropOptions<boolean>
  },
  data () {
    return {
      year: new Date().getFullYear()
    };
  }
});
</script>

<style scoped>
.layout-footer {
  text-align: center;
  color: #888;
  user-select: none;
  padding: 24px 0;
}

@media (max-width: 576px) {
  .record-info,
  .admin-link {
    display: none;
  }
}
</style>