<template>
  <div>
    <h2>{{ title }}</h2>
    <div v-if="renderFn">
      <component :is="renderFn($createElement)"></component>
    </div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'ComponentA',
  props: {
    title: {
      type: String,
      default: 'Title',
    },
    renderFn: {
      type: Function,
      default: null,
    },
  },
  data() {
    return {
      title: this.title,
      renderFn: this.renderFn,
    }
  },
}
</script>
