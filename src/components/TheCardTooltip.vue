<template>
  <div class="tooltip">
    <div class="tooltip-author">
      <div>
        <slot name="tooltip-author">author name</slot>
      </div>
      <div>
        <slot name="tooltip-img">person face</slot>
      </div>
    </div>
    <hr>
    <div class="fan">
      <div>
        <slot name="tooltip-fan">fan</slot>
      </div>
      <div>
        <slot name="tooltip-button">button</slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "TheCardTooltip"
};
</script>
<style lang="scss" >
$color-black: #000;
.tooltip {
  position: absolute;
  height: 100px;
  padding: 10px;
  border: 1px solid rgba(0, 0, 0, 0.1);
  z-index: 1;
  background: #fff;
  border-radius: 6px;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.1);
}
.tooltip::after {
  content: "";
  position: absolute;
  top: 95%;
  left: 50%;
  width: 10px;
  height: 10px;
  transform: rotate(45deg);
  background: #fff;
  box-shadow: 1px 1px 1px -1px $color-black;
}
hr {
  margin: 0 20px;
}
.fan {
  display: flex;
  justify-content: space-between;
  padding: 20px;
}
.tooltip-author {
  display: flex;
  justify-content: space-between;
  padding: 10px;
}
</style>
