<template>
  <div>
    <div>
      <slot>header</slot>
    </div>
    <div>
      <slot>body</slot>
    </div>
    <div>
      <slot>foot</slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheCard'
}
</script>