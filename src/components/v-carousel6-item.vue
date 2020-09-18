<template>
  <div class="v-carousel2-item">
    <div class="wrapper-one">
    <img class="d-block" :src="require('@/assets/images/section-2/' + item2_data.img) " alt="">
<!--    <b-img class="d-block" :src="require('@/assets/images/section-2/' + item_data.img) " alt=""></b-img>-->
      <div class="wrap-text-data d-block">
      <br>
      <span class="text_pay" style="text-align: left" :text="item2_data.text_pay">{{ item2_data.text_pay }}</span>
      <br>
      <h5 class="text_title"  :text="item2_data.text_title">{{ item2_data.text_title }}</h5>


      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "v-carousel2-item",
  props: {
    item2_data: {
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

.wrapper-one img{
  min-width: 360px;
  padding-left: 1em;
  padding-right: 1em;
}

.wrap-text-data {
  padding-left: 1em;
  padding-right: 1em;
}

.v-carousel2-item {

  /*min-width: 796px;*/
  /*max-width: 75%;*/
  /*margin-right: 2em;*/
  /*margin-left: 2em;*/
  /*height: 300px;*/
  /*border: 1px solid red;*/
  /*border: 1px solid #EFEFEF;*/
}

@media (max-width: 992px) {
  /*.v-carousel2-item {*/
  /*  max-width: 100%;*/
  /*}*/
}

.v-carousel2-item img {
  max-width: 350px;
  min-width: 350px;
  /*max-width: 263px;*/
  /*max-width: 33%;*/
  /*height: 100%;*/
}
.v-carousel2-item .text-content {
  /*max-width: 526px;*/
  /*height: 100%;*/
}

.carousel2-item {
  display: inline-block;
}

.text_title {
  text-align: left!important;
}

</style>
