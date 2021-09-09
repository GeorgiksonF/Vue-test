<template>
  <div class="slider__item" :style="{background: color}"></div>
</template>

<script>
export default {
  name: 'App',
  props: ['color'],
  data() {
    return {
    }
  },
}
</script>