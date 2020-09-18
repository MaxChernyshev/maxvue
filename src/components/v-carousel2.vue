<template>
  <div class="wrapper">
    <button @click="prevSlide">prev</button>
    <button @click="nextSlide">next</button>

    <div class="v-carousel1" :style="{'margin-left': '-' + (widthmon * currentSlideIndex) + '%'}">
      <vCarousel1Item class="v-carousel1"
                      v-for="item in carousel_data"
                      :key="item.id"
                      :item_data="item"

      >
      </vCarousel1Item>
    </div>
<!--    <p>Current width is: {{ windowWidth }}</p>-->
<!--    <p>Current width is: {{ widthmon }}</p>-->
  </div>
</template>

<script>
import vCarousel1Item from './v-carousel1-item.vue'

export default {
  name: "v-carousel1",
  components: {
    vCarousel1Item,
  },
  props: {
    carousel_data: {
      type: Array,
      default: () => [],
    }
  },
  data() {
    return {
      currentSlideIndex: 0,
      itemSize: null,
      windowWidth: window.innerWidth,
      widthmon: this.widthmon,
    }
  },
  computed: {},
  methods: {
    nextSlide() {
      if (this.currentSlideIndex >= this.carousel_data.length - 1) {
        this.currentSlideIndex = 0
      } else {
        this.currentSlideIndex++
        // console.log(window['screen'].width)
      }
    },
    prevSlide() {
      if (this.currentSlideIndex > 0) {
        this.currentSlideIndex--
      }
    }
  },

  mounted () {
    // this.widthmon = 75
    window.onresize = () => {
      this.windowWidth = window.innerWidth;
      if(this.windowWidth < 962) {
        this.widthmon = 100
      }
      else {
        this.widthmon = 75
      }
    };
  },

}
</script>

<style scoped>
.wrapper {
  /*margin: auto;*/
  /*max-width: 50%;*/
  /*max-width: 278px;*/
  overflow: hidden;
}

.v-carousel1 {
  display: flex;
  transition: all ease 0.5s;
}

</style>
