<template >
  <div class="container">
    <div class="row">
      <div
        class="col-lg-3 col-md-6 col-12 form-group show-img"
        v-for="(item, index) in dataImg"
        :key="index"
      >
       <transition name="slide-fade">
        <img
        v-show="show"
          @click="onImgClick(index)"
          :src="require(`~/assets/img/${item.source}`)"
          class="img-r img-fluid img-thumbnail"
        />
         </transition>
      </div>
    </div>
    <div class="row">
      <div class="col-12" style="text-align:center">
        <nuxt-link to="/" class="btn btn-dark">Back to Profile</nuxt-link>
      </div>
    </div>
    <ModalImg :startImg="startImg" :dataImages="dataImg" @modalHide="onModalHide"></ModalImg>
  </div>
</template>
<script>
import ModalImg from "@/components/gallery/modalImg.vue";
export default {
  components: { ModalImg },
  data() {
    return {
      dataImg: [],
      totalImg: 12,
      sliding: null,
      startImg: 0,
      show: false
    };
  },

  mounted() {
    this.$nextTick(() => {
      this.show = true
    })
  },
  created() {
    for (let i = 1; i <= this.totalImg; i++) {
      const numberImg = i.toString().padStart(2, "0");
      this.dataImg = [
        ...this.dataImg,
        { id: i, source: `fruit-${numberImg}.jpg` },
      ];
    }
  },
  methods: {
    onModalHide () {
      this.startImg = 0
    },
    onImgClick(index) {
      this.startImg = index
      this.$bvModal.show("my-modal");
    },
  },
};
</script>
<style >
img.img-r {
  height: 200px;
  width: 200px;
  cursor: pointer;
}
div.show-img {
  text-align: center;
}
.slide-fade-enter-active {
  transition: all 2s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>