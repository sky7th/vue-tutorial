<template>
  <div 
    :style="{ width: width + 'px', height: height + 'px'}"
    :class="['box', color]"></div>
</template>

<script>
export default {
  props: {
    color: { type: String, default: ''}
  },
  data() {
    return {
      width: 40,
      height: 80
    }
  }
}
</script>

<style scoped>
.box {
  border: 1px solid #000;
}
.blue {
  background: #009bff;
}
.purple {
  background: #8f46ff;
}
.green {
  background: #00bcac;
}
</style>