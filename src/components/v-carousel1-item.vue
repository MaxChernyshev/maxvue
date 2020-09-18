<template>
  <div class="v-carousel1-item">
<!--    <div class="carousel-item">-->
      <img class="d-inline" :src="require('@/assets/images/section-1/' + item_data.img) " alt="">
      <div class="text-content d-inline">
        <p :text="item_data.text_title">{{ item_data.text_title }}</p>
        <p :text="item_data.text_theme">{{ item_data.text_theme }}</p>
        <p :text="item_data.text_quote">{{ item_data.text_quote }}</p>
      </div>
<!--    </div>-->
  </div>
</template>

<script>

export default {
  name: "v-carousel1-item",
  props: {
    item_data: {
      type: Object,
      default: () => {
      }
    }
  },
  data() {
    return {}
  },

}
</script>

<style>
.v-carousel1-item {
  min-width: 796px;
  /*max-width: 75%;*/
  /*margin-right: 2em;*/
  /*margin-left: 2em;*/
  /*height: 300px;*/
  border: 1px solid red;
  /*border: 1px solid #EFEFEF;*/
}

@media (max-width: 992px) {
  .v-carousel1-item {
    max-width: 100%;
  }
}

.v-carousel1-item img {
  max-width: 263px;
  /*max-width: 33%;*/
  /*height: 100%;*/
}
.v-carousel1-item .text-content {
  max-width: 526px;
  /*height: 100%;*/
}

.carousel-item {
  /*display: inline-block;*/
}

</style>
