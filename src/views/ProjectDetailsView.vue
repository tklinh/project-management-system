<template>
    <a-tabs v-model:activeKey="activeKey">
    <a-tab-pane key="1">
      <template #tab>
        <span>
          <SecurityScanOutlined />
          Pháp lý
        </span>
      </template>
      <ProjectLegacy />
    </a-tab-pane>
    <a-tab-pane key="2">
      <template #tab>
        <span>
          <DollarCircleOutlined />
          Tài chính
        </span>
      </template>
      <ProjectFinance />
    </a-tab-pane>
    <a-tab-pane key="3">
      <template #tab>
        <span>
          <ToolOutlined />
          Xây dựng
        </span>
      </template>
      <ProjectConstruction />
    </a-tab-pane>
  </a-tabs>
</template>
<script setup lang="ts">
import { SecurityScanOutlined, DollarCircleOutlined, ToolOutlined } from '@ant-design/icons-vue';
import { ref } from 'vue';

import ProjectLegacy from '@/components/ProjectLegacy.vue';
import ProjectFinance from '@/components/ProjectFinance.vue';
import ProjectConstruction from '@/components/ProjectConstruction.vue';

const activeKey = ref('1');
</script>