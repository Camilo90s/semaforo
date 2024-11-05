
<template>
  <div :class="['light', 'green', { on: isOn }]"></div>
</template>

<script>
export default {
  props: {
    isOn: Boolean,
  },
};
</script>

<style scoped>
.light {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background-color: #555;
  opacity: 0.3; /* Luz apagada */
  transition: opacity 0.3s ease;
}

.light.on {
  opacity: 1; /* Luz encendida */
}

.green {
  background-color: green;
}
</style>
