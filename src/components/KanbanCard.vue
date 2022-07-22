<template>
  <div class="kanban-card">
    Value: {{ foo }}
  </div>
</template>

<script>
export default {
  inject: {
    foo: {
      default: 'default value',
    }
  },
}
</script>
