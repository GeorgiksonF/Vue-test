<template>
  <div class="slider">
    <div class="slider__items">
      <button @click="showPrev">Prev</button>
      <SliderItem v-for="item in currentSliderItem" :key="item.id" :color="item.color"/>
      <button @click="showNext">Next</button>
    </div>
    <div class="slider__dots">
      <div class="slider__dot" 
      v-for="item in sliderItems" 
      :key="item.id" 
      :class="[item.isCurrent && 'slider__dot--active']"
    ></div>
    </div>
  </div>
</template>

<script>
import SliderItem from './SliderItem.vue'
export default {
  name: 'App',
  components: {
    SliderItem
  },
  data() {
    return {
      sliderItems: [
        {id: 0, color: "red", isCurrent: true},
        {id: 1, color: "blue", isCurrent: false},
        {id: 2, color: "yellow", isCurrent: false},
        {id: 3, color: "green", isCurrent: false},
      ]
    }
  },
  methods: {
    showNext: function () {
      let current = this.sliderItems.find(item => item.isCurrent);
      current.isCurrent = false
      if (current.id === this.sliderItems.length - 1) {
        return this.sliderItems[0].isCurrent = true;
      }
      return this.sliderItems[current.id + 1].isCurrent = true;
    },
    showPrev: function () {
      let current = this.sliderItems.find(item => item.isCurrent);
      current.isCurrent = false
      if (current.id === 0) {
        return this.sliderItems[this.sliderItems.length - 1].isCurrent = true;
      }
      return this.sliderItems[current.id - 1].isCurrent = true;
    },
  },
  computed: {
    currentSliderItem: function () {
      return this.sliderItems.filter(item => item.isCurrent)
    }
  }
}
</script>