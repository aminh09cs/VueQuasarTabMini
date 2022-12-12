<template>
  <Tab title="Your Quasar Tabs">
    <template v-slot:header>
      <div class="tab-content-header" v-for="(item, idx) in listTab" :key="idx" @click="onChangeTab(idx)"
        :class="isActive === idx + 1 ? 'active' : ''">
        {{ item.name }}
      </div>
    </template>
    <template v-slot:content>
      <div class="tab-content-content" v-for="(item, idx) in listTab.filter(info => info.id === isActive)" :key="idx">
        {{ item.content }}
      </div>
    </template>
  </Tab>
</template>

<script setup>
import { ref } from 'vue';
import Tab from '../components/Tab.vue';

const listTab = ref([
  {
    id: 1,
    name: 'Mails',
    content: 'MAIL Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero, Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero',

  },
  {
    id: 2,
    name: 'Alarms',
    content: 'ALARMS Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero, Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero'
  },
  {
    id: 3,
    name: 'Movies',
    content: 'MOVIES Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero, Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero'
  },
])
const isActive = ref(1);
const onChangeTab = (idx) => {
  isActive.value = idx + 1;
}

</script>
<style>

</style>