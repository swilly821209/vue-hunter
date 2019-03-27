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
  margin: 15px 0;
}
.fan {
  display: flex;
  justify-content: space-around;
  margin-bottom: 5px;
}
.tooltip-author {
  display: flex;
  justify-content: space-between;
}
</style>
