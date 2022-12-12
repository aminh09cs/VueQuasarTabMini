<template>
  <header class="tab-title">
    <h1>{{ title }}</h1>
  </header>
  <section class="tab-content">
    <div class="header">
      <slot name="header"></slot>
    </div>
    <div class="content">
      <slot name="content"></slot>
    </div>
    <slot></slot>
  </section>
</template>
<script setup>
import { defineProps } from 'vue';
const props = defineProps({
  title: String,
})
</script>
<style lang="scss">
.tab-content {
  display: flex;
  width: 80%;
  margin: 0 auto;
  margin-top: 50px;
  border: 2px solid #ddd;

  .header {
    border-right: 2px solid #ddd;

    .tab-content-header {
      padding: 15px;
      color: #26A69A;
      cursor: pointer;
      border-right: 2px solid transparent;
    }

    .tab-content-header.active {
      border-right: 2px solid #26A69A;
    }
  }

  .content {
    padding: 20px;
    height: 150px;
    overflow-y: auto;
  }

  ::-webkit-scrollbar {
    display: none;
  }
}
</style>