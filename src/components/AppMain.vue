<script>
export default {
  data() {
    return { 
      
    }
  }
}
</script>

<template>
  <div class="d-flex">

    <!-- Container Cat Image and statistics -->
      <div class="text-center">

        <div>

        </div>

        <!-- Stats -->
        <div class="d-flex justify-content-center">
          <div class="d-flex align-items-center pe-3">
            <lord-icon
                src="https://cdn.lordicon.com/sxfkrohm.json"
                trigger="hover"
                stroke="light"
                colors="primary:#121331,secondary:#dda0dd"
                style="width:40px;height:40px">
            </lord-icon>
            Hunger
          </div>
          <div class="d-flex align-items-center pe-3">
            <lord-icon
              src="https://cdn.lordicon.com/bpwrqrbv.json"
              trigger="hover"
              stroke="light"
              colors="primary:#fff176,secondary:#000000"
              style="width:40px;height:40px">
          </lord-icon>
          Happiness
          </div>
          <div class="d-flex align-items-center pe-3">
            <lord-icon
              src="https://cdn.lordicon.com/uppnozfl.json"
              trigger="hover"
              stroke="light"
              colors="primary:#121331,secondary:#ff1493"
              style="width:40px;height:40px">
            </lord-icon>
            Energy
          </div>
        </div>
      </div>

      <!-- Buttons -->
      <button id="eat_btn">
        Nutri
      </button>
      <button id="eat_btn">
        Gioca
      </button>
      <button id="eat_btn">
        Accarezza
      </button>
      <button id="eat_btn">
        Metti a dormire
      </button>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

h1 {
  text-align: center;
}

#eat_btn  {

}


</style>
