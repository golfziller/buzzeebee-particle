<template >
  <div>
    <b-modal id="my-modal" size="xl" centered hide-footer>
      <template #modal-title>Firut <code>images </code></template>
     <b-carousel
      v-model="slide"
      :interval="2000"
       fade
      controls
      indicators
    >
      <b-carousel-slide   v-for="(item,index) in dataImages" :key="index">
        <template #img>
           <img
            class="d-block img-fluid mx-auto "
            style="height:480px;"
            :src="require(`~/assets/img/${item.source}`)"
            alt="image slot"
          >
        </template>
        
      </b-carousel-slide>
    </b-carousel>
    </b-modal>
  </div>
</template>
<script>
export default {
  props: {
    startImg: Number,
    dataImages: {
      type: Array,
      default: () => []
    }
  },
  watch: {
    startImg: function(newVal) {
      this.slide = newVal
    }
  },
    data() {
        return {
            slide: 0,
        }
    },
};
</script>
<style lang="">
</style>