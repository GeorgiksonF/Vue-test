<template>
  <div id="app">
    <div class="container">
      <Slider/>
    </div>
  </div>
</template>

<script>
import Slider from './components/Slider.vue'
import './scss/main.scss'

export default {
  name: 'App',
  components: {
    Slider
  }
}
</script>
