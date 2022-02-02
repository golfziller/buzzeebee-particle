<template >
  <div class="container">
    <div class="row">
      <div
        class="col-lg-3 col-md-6 col-12 form-group show-img"
        v-for="(item, index) in dataImg"
        :key="index"
      >
        <img
          @click="onImgClick(index)"
          :src="require(`~/assets/img/${item.source}`)"
          class="img-r img-fluid img-thumbnail"
        />
      </div>
    </div>
    <ModalImg :startImg="startImg" :dataImages="dataImg"></ModalImg>
  </div>
</template>
<script>
import ModalImg from "./components/modalImg.vue";
export default {
  components: { ModalImg },
  data() {
    return {
      dataImg: [],
      totalImg: 12,
      sliding: null,
      startImg: 0
    };
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
</style>