<template>
  <div class="wrapper">
    <b-row class="row-section2-1 pt-3 pb-3 pl-2 pr-2 d-flex flex-row">
      <b-col cols="6" class="magazin-title">Журнал AllRetail</b-col>
      <b-col cols="4" class="text-right">Травень, 2019</b-col>
      <b-col cols="2" class="text-right">
          <button class="slider2-button" @click="prevSlide2">&lt;</button>
          <button class="slider2-button">|</button>
          <button class="slider2-button" @click="nextSlide2">&gt;</button>
      </b-col>
    </b-row>


    <div class="v-carousel2"  :style="{'margin-left': '-' + (100 * currentSlide2Index) + '%'}">
      <vCarousel2Item
                      v-for="item in carousel2_data"
                      :key="item.id"
                      :item2_data="item"
      >
      </vCarousel2Item>
    </div>
  </div>
</template>

<script>
import vCarousel2Item from './v-carousel2-item.vue'

export default {
  name: "v-carousel2",
  components: {
    vCarousel2Item,
  },
  props: {
    carousel2_data: {
      type: Array,
      default: () => [],
    }
  },
  data() {
    return {
      currentSlide2Index: 0,
      itemSize: null,
    }
  },
  computed: {},
  methods: {
    nextSlide2() {
      if (this.currentSlide2Index >= this.carousel2_data.length - 1) {
        this.currentSlide2Index = 0
        console.log(this.currentSlide2Index)
        console.log('aaaaaaaaaaa')
      } else {
        this.currentSlide2Index++
      }
    },
    prevSlide2() {
      if (this.currentSlide2Index > 0) {
        this.currentSlide2Index--
      }
    }
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

.v-carousel2 {
  display: flex;
  transition: all ease 0.5s;
  margin-top: 2em;
}

.slider2-button {
  background: none;
  border: 0;
}

.row-section2-1 {
  background-color: #F2F2F2;
}
.magazin-title {
  text-align: left;
  font-weight: bold;
  font-size: 18px;
  line-height: 25px;
  color: #424242;
}

</style>
