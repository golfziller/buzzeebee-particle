<template >
  <div>
    <b-modal
      id="my-modal"
      size="xl"
      scrollable
      centered
      hide-footer
      @hide="onHide"
    >
      <template #modal-title>Firut <code>images </code></template>
      <b-carousel v-model="slide" :interval="2000" fade controls indicators>
        <b-carousel-slide v-for="(item, index) in dataImages" :key="index">
          <template #img>
            <div class="show-img">
              <img
                class="img-show img-fluid d-block mx-auto"
                :src="require(`~/assets/img/${item.source}`)"
                alt="image slot"
              />
            </div>
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
      default: () => [],
    },
  },
  watch: {
    startImg: function (newVal) {
      this.slide = newVal;
    },
  },
  data() {
    return {
      slide: 0,
    };
  },
  methods: {
    onHide() {
      this.$emit("modalHide");
    },
  },
};
</script>
<style scoped>
div.show-img {
  height: 400px;
}
.img-show {
  max-height: 400px;
  width: auto;
}
@media only screen and (max-width: 768px) {
  div.show-img {
    height: 350px;
  }
}
@media only screen and (max-height: 420px) {
  div.show-img {
    height: auto;
  }
  .img-show {
    height: auto;
    width: 100%;
  }
}
</style>