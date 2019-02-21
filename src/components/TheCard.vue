<template>
  <div>
    <div>
      <slot name="header">header</slot>
    </div>
    <div>
      <slot name="body">body</slot>
    </div>
    <div>
      <slot name="foot">foot</slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheCard'
}
</script>