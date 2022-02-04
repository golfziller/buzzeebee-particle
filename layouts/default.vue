<template >
  <div>
    <TheHeader ></TheHeader>
    <div class="app-container">
       <Nuxt></Nuxt>
    </div>
    <TheFooter></TheFooter>
  </div>
</template>
<script>
import TheHeader  from "@/components/layouts/TheHeader.vue";
import TheFooter  from "@/components/layouts/TheFooter.vue";
export default {
   name: 'layout',
  components: {
    TheHeader,TheFooter
  },
};
</script>
<style >
   .app-container {
      padding: 20px;
      padding-bottom: 70px;
      display: flex;
   }
</style>