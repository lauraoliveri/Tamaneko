<script>
export default {
  data() {
    return { 
      hunger: 100,
      happiness: 100,
      energy: 100,
      currentSprite: 'src/assets/images/Sprites/Default.png',
      defaultSprite: 'src/assets/images/Sprites/Default.png',
      sprites: [
        'src/assets/images/Sprites/Eating.png',
        'src/assets/images/Sprites/Playing.png',
        'src/assets/images/Sprites/Cute.png',
        'src/assets/images/Sprites/Sleeping.png'
      ]
    }
  },
  methods: {
    feedCat(){
      this.hunger += 30;

      if (this.hunger > 100) {
        this.hunger = 100;
      }
    },
    petCat(){
      this.happiness += 15;

      if (this.happiness > 100) {
        this.happiness = 100;
      }
    },
    playWithCat() {
      this.happiness += 10;

      if (this.happiness > 100) {
        this.happiness = 100;
      }
    },
    putCatToSleep(){
      this.energy += 20;

      if (this.energy > 100) {
        this.energy = 100;
      }
    },
    changeSprite(newUrl) {
      this.currentSprite = newUrl;

      // After 2 seconds the sprite changes
      setTimeout(() => {
        this.currentSprite = this.defaultSprite; 
      }, 4000);
    }
  },
  mounted() {

    // hunger decreasing timer
    let hungerTimer = setInterval(() => {
      this.hunger -=10;

      if (this.hunger == 0) {
        clearInterval(hungerTimer);
      }
    }, 10000);

    // happiness decreasing timer
    let happinessTimer = setInterval(() => {
      this.happiness -=10;

      if (this.happiness == 0) {
        clearInterval(happinessTimer);
      }
    }, 5000);

    // energy decreasing timer
    let energyTimer = setInterval(() => {
      this.energy -=20;

      if (this.energy == 0) {
        clearInterval(energyTimer);
      }
    }, 15000);

    
  }
}
</script>

<template>
  <div class="main">

    <!-- Container Cat Image and statistics -->
      <div id="screen">

        <!-- Stats -->
        <div class="d-flex justify-content-center p-2">
          <div class="d-flex align-items-center pe-3">
            <lord-icon
              src="https://cdn.lordicon.com/kfxkchht.json"
              trigger="hover"
              style="width:40px;height:40px">
            </lord-icon>

            <!-- Hunger Rate -->
            Hunger: {{ hunger }}%
          </div>
          <div class="d-flex align-items-center pe-3">
            <lord-icon
              src="https://cdn.lordicon.com/heacsgdl.json"
              trigger="hover"
              colors="primary:#000000,secondary:#fad3d1"
              style="width:30px;height:30px">
            </lord-icon>

            <!-- Happiness Rate -->
            Happiness: {{ happiness }}%
          </div>
          <div class="d-flex align-items-center pe-3">
            <lord-icon
              src="https://cdn.lordicon.com/dqhmanhc.json"
              trigger="hover"
              colors="primary:#ff1493,secondary:#ebe6ef,tertiary:#ffc738,quaternary:#f9c9c0,quinary:#f24c00"
              style="width:30px;height:30px">
            </lord-icon>

            <!-- Energy Rate -->
            Energy: {{ energy }}%
          </div>
        </div>

        <div id="sprite" :style="{ backgroundImage: `url(${currentSprite})` }">

        </div>

        
      </div>

      <!-- Buttons -->
      <div class="text-center" id="btn_container">
        <button id="eat_btn" @click="() => { feedCat(); changeSprite(sprites[0]); }" >
          Nutri
        </button>
        <button id="eat_btn" @click="() => { playWithCat(); changeSprite(sprites[1]); }">
          Gioca
        </button>
        <button id="eat_btn" @click="() => { petCat(); changeSprite(sprites[2]); }">
          Accarezza
        </button>
        <button id="eat_btn" @click="() => { putCatToSleep(); changeSprite(sprites[3]); }">
          Metti a dormire
        </button>
      </div>
  </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

.main {
  height: 80vh;
  background-color: $fucsia;
  padding: 50px;
}

#screen {
  background-color: $dirtyWhite;
  width: 600px;
  height: 400px;
  margin: 0 auto;
  padding: 5px;
  border: 5px solid $yellow;
}

#sprite {
  width: 224px;
  height: 224px; 
  margin: 0 auto;
  margin-top: 60px;
  background: no-repeat;
  background-size: contain;
}



#btn_container {
  padding-top: 40px;
  margin-bottom: 50px;
}

button {
  height: 50px;
  padding: 10px;
  margin-right: 10px;
  border-radius: 50px;
}


</style>
