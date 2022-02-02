<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6">
        <img
          src="~/assets/img/profile-1.jpg"
          class="img-thumbnail rounded-circle"
        />
      </div>
      <div class="col-md-6">
        <h3>Pongtorn Kitwimonrattana</h3>
        <h4><code><i>Fontend Develop</i></code></h4>
        <p><strong>Nick name: Golf</strong></p>
        <p><strong>Date of Birth: 3 June, 1994</strong></p>
        <p><strong>Age: 27</strong></p>
        <p><strong>Nationality: THAI</strong></p>
      </div>
    </div>
    <div class="row">
      <div class="col-12">
        <p class="text-indent">
          <strong>I am a developer </strong> to find an opportunity to gain more
          learning new skills and enjoy working in software and learning new
          things. I am a professional person with excellent communications
          skills and time management. My greatest passion is to using my
          technical know-how to benefit other people and organization and
          develop my skill continuously.
        </p>
      </div>
    </div>
    <div class="row">
      <div class="col-12">
        <h5>S K I L L S S U M M A R Y</h5>
        <h6 >Vue Js</h6>
        <div class="progress">
          <div
            class="progress-bar bg-success"
            role="progressbar"
            :style="`width: ${perCentVue}%`"
            aria-valuenow="25"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>
        <h6 >Vuex</h6>
        <div class="progress">
          <div
            class="progress-bar bg-info"
            role="progressbar"
            :style="`width: ${perCentVuex}%`"
            aria-valuenow="25"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>
        <h6 >Vue Router</h6>
        <div class="progress">
          <div
            class="progress-bar bg-danger"
            role="progressbar"
             :style="`width: ${perCentVueRouter}%`"
            aria-valuenow="25"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>
         <h6 >React Js</h6>
        <div class="progress">
          <div
            class="progress-bar bg-warning"
            role="progressbar"
            :style="`width: ${perCentReact}%`"
            aria-valuenow="25"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>
        <h6 >CSS</h6>
        <div class="progress">
          <div
            class="progress-bar "
            role="progressbar"
            :style="`width: ${perCentCss}%`"
            aria-valuenow="25"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>
        <h6 >HTML</h6>
        <div class="progress">
          <div
            class="progress-bar bg-secondary"
            role="progressbar"
            :style="`width: ${perCentHtml}%`"
            aria-valuenow="25"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>
      </div>
    </div>
    <div class="row " style="margin-top: 20px">
      <div class="col-12 text-center" >
       <nuxt-link to="/gallery" class="btn btn-info" >Let See Gallery</nuxt-link> 
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Profile",
  data () {
    return {
      perCentHtml: 0,
      perCentCss: 0,
      perCentReact: 0,
      perCentVueRouter: 0,
      perCentVuex: 0,
      perCentVue: 0
    }
  },
  mounted() {
    setTimeout(() => {
      this.perCentHtml = 40,
      this.perCentCss = 40,
      this.perCentReact = 50,
      this.perCentVueRouter = 65,
      this.perCentVuex = 60,
      this.perCentVue = 70
    }, 500)
  },
};
</script>
<style>
p.text-indent {
  text-indent: 40px;
}
</style>
