<template>
  <div class="tdesign-demo-block-column">
    <div class="tdesign-demo-block-row">
      <t-switch v-model="slotChecked" size="large">
        <template #label="slotProps">{{ slotProps.value ? '开' : '关' }}</template>
      </t-switch>
      <t-switch size="large">
        <template #label="slotProps">
          <template v-if="slotProps.value">
            <check-icon />
          </template>
          <template v-else>
            <close-icon />
          </template>
        </template>
      </t-switch>
    </div>

    <div class="tdesign-demo-block-row">
      <t-switch v-model="checked" size="large" :label="['开', '关']"></t-switch>
      <t-switch size="large" :label="['开', '关']"></t-switch>
    </div>

    <div class="tdesign-demo-block-row">
      <t-switch v-model="renderChecked" size="large" :label="[renderActiveContent, renderInactiveContent]"></t-switch>
      <t-switch size="large" :label="[renderActiveContent, renderInactiveContent]"></t-switch>
    </div>

    <div class="tdesign-demo-block-row">
      <t-switch v-model="renderChecked2" size="large" :label="renderContent"></t-switch>
      <t-switch size="large" :label="renderContent"></t-switch>
    </div>
  </div>
</template>
<script setup lang="jsx">
import { ref } from 'vue';

import { CloseIcon, CheckIcon } from 'tdesign-icons-vue-next';

const checked = ref(true);
const renderChecked = ref(true);
const renderChecked2 = ref(true);
const slotChecked = ref(true);

const renderActiveContent = () => {
  return <CheckIcon />;
};
const renderInactiveContent = () => {
  return <CloseIcon />;
};
const renderContent = (h, data) => {
  return data.value ? <CheckIcon /> : <CloseIcon />;
};
</script>

<style scoped>
.switch-demo .tdesign-demo-block {
  width: 150px;
  display: flex;
  justify-content: space-around;
}
</style>
