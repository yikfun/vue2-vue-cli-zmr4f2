<template>
  <div>
    <component-a :title="'Custom Title'" :render-fn="renderFn">
      <template v-slot:default>
        <p>This is the content of Component A</p>
      </template>
    </component-a>
  </div>
</template>

<script>
import ComponentA from './components/A.vue'
import ComponentB from './components/B.vue'

export default {
  name: 'App',
  components: {
    ComponentA,
    ComponentB,
  },
  methods: {
    renderFn($createElement) {
      return $createElement(ComponentB)
    },
  },
}
</script>
