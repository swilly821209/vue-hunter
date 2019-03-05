<template>
  <div>
    <div>
      <slot name="cardHeader">header</slot>
    </div>
    <div>
      <slot name="cardBody">body</slot>
    </div>
    <div>
      <slot name="cardFoot">foot</slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "TheCard"
}
</script> 
