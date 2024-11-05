
<template>
  <div :class="['light', 'red', { on: isOn }]"></div>
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
  opacity: 0.3; 
  transition: opacity 0.3s ease;
}

.light.on {
  opacity: 1;
}

.red {
  background-color: red;
}
</style>
